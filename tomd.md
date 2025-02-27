# My Projects TODO List

## HD2 Audio Modding Tool (New UI)

### Something To Remind Myself

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
   render loop, and then collect the result.
  - Make sure to minimize the amount of sharing (reduce resource competition) and coping if isolation
   is done by computing / create a set of state, and throw away the old one.
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

### Porting Features

- Load an archive on an existence Mod window
- Sound bank viewer
  - Hierarchy View
  - Source View

### Guide & Tutorial

1. Target Import Automation
    1. CSV
    2. Manifest
2. Patch Import Automation
