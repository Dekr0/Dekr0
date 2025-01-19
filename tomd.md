# My Projects TODO List

## HD2 Audio Modding Tool (New UI)

## Something To Remind Myself

- Maintain [nonpessmization and simplicity](https://youtu.be/pgoetgxecw8?t=372)
  - Sweeps for unecessary opertaions and complexities, and remove them.
- [Slow code isolation](https://youtu.be/lStYLF6Us_Q?si=fy9ePITN6oMy6dvF)
- The following operations should be queued, scheduled, and ran in the background:
  - most IO operations,
  - operations that are irrelevant to a frame of rendering,
  - ???
- If it cannot be done in this way due to other reasons (e.g., there is data that is required
 by a frame of render), they should be either
  - ran before the new frame and after the previous frame is rendered and displayed
  on the screen,
  - queued, scheduled, and ran in the background, and then check for its completion between each
   render loop, and then collect the result. Make sure to minimize the amount of sharing (reduce
   resource competition) and coping.
- Minmize the amount of source of truth.

### Performance

- The memory usage doesn't seems right. Without any active loaded archive, it sit around 70 ~ 90 MB.
  - The original implementation with Tkinter is only around 32 MB.
- The memory doesn't immedately released when a bank file explorer is closed. Especially, when loading
archive such as `weapon_superearth` and closing it after uses, the collection does not happen unless
another few instances of large archives are opened.
  - This issue exists in the implementation with Tkinter as well.
- High GPU usage (Idle is at 12%).
- Disable rendering / lower max frame rate when it's idle. (Fixed)
- Use clipper to save on computation for large amount table items.

### UI Styling

- Context menu (Done)

### Porting Features

- Information copying
  - Copy Audio ID (Done)
  - Copy ID (All types of hierarchy entries)
    - Fold
    - Unfold   
- Configuration storage (Done)
- Database integration (Done)
  - Display label (Done)
  - Rename label (Working on data sync.)
- Audio Export
- Manifest generation
  - Target Import Automation
    - CSV
    - JSON
    - Based off label, and tags
  - Patch Import Automation
  - Patch manifest generation

#### Features

- Table
  - Fold all items
- Focus on a bank viewer when users try to load the same file.
- Allow to duplicate a bank viewer (only visually)

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

## HD2 SFX Mods

- MG43 and M105 does not share sounds after loaded two patches that modified the shared part. They doesn't seems to be effecting each other.
