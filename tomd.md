# My Projects TODO List

## HD2 Audio Modding Tool (New UI)

### Performance 

- Trim unnecessary instructions
- Cached in as much computation from backend for the UI while slowly reworking the backend.
- The memory usage doesn't seems right. Without any active loaded archive, it sit around 70 ~ 90 MB.
  - The original implementation with Tkinter is only around 32 MB.
- The memory doesn't immedately released when a bank file explorer is closed. Especially, when loading
archive such as `weapon_superearth` and closing it after uses, the collection does not happen unless
another few instances of large archives are opened.
  - This issue exists in the implementation with Tkinter as well.
- High GPU usage (Idle is at 12%).

### UI Styling

- Context menu (Done)

### Porting Features

1. Information copying
  a. Copy Audio ID
  b. Copy ID (All types of hierarchy entries)
     - Fold
     - Unfold   
2. Configuration storage
3. Database integration
   a. Display label
   b. Rename label
5. Audio Export
6. Manifest generation
   a. Target Import Automation
     - CSV
     - JSON
   b. Patch Import Automation
   c. Patch manifest generation

## HD2 Audio Modding Tool (Legacy)

### Features

#### Random Sequence Container

1. Random Sequence Container parameters
    1. Parsing
        1. Rapid testing
    2. Displaying information on the UI
    3. Changing parameters
        1. core logic 
        2. changing parameters via UI

#### Information Copying

- Rework "Copy IDs -> Linear"
    - It should be "Copy Audio Source IDs" only.
    - There's no need to do folding for just copying audio ids because I still need to unfold it.

### Guide & Tutorial

1. Target Import Automation
    1. CSV
    2. Manifest
2. Patch Import Automation

### PR

1. Push Automation and QOL branch.
