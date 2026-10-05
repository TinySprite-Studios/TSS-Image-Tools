# TSS Image Tools

TSS Image Tools is a Windows app for processing single images or batches.

## Quick Start
1. Extract the whole release folder, keeping `models`, `licenses`, `assets`, and the DLLs beside `TssImageTools.App.exe`, then run it.
2. Add files with `Add Files` or `Add Folder`.
3. Choose your `Action`.
4. Set `Output Root Folder`.
5. Check preview (for Watermark and Remove Background).
6. Click `Start Processing`.
7. On completion, use `View Files` to open the output folder.

## Queue Limits
- Convert, Resize, Compress: up to `5000` files
- Watermark: up to `100` files
- Remove Background: up to `50` files

## Output Location
The app writes new files only (non-destructive):
`<your selected output folder>/exported_images/yyyy-MM-dd_HH-mm-ss/`

Original images are never deleted or overwritten.

## Modules

### 1. Convert
Convert image format between:
- PNG
- JPG
- WEBP
- GIF (single-frame output)
- BMP
- ICO

Steps:
1. Select `Action: Convert`
2. Choose `Convert To`
3. Start processing

### 2. Resize
Resize images to exact pixel dimensions.

Fill modes:
- `Stretch`: forces exact width/height
- `Center`: keeps aspect, centers on canvas
- `Fit`: keeps aspect inside target bounds

Steps:
1. Select `Action: Resize`
2. Set width and height
3. Choose fill mode
4. Start processing

### 3. Compress
Reduce file size using quality setting.

Steps:
1. Select `Action: Compress`
2. Set `Quality (1-100)`
3. Start processing

### 4. Watermark
Add either text watermark or image watermark.

Watermark type:
- `Text`
- `Image`

Anchor positions:
- TopLeft, TopCenter, TopRight
- LeftCenter, Center, RightCenter
- BottomLeft, BottomCenter, BottomRight
- `Span` (tiles watermark across image with transparency)

Available controls:
- Opacity
- Margin
- Text size (text mode)
- Image scale (image mode)

Steps:
1. Select `Action: Watermark`
2. Choose watermark type
3. Enter watermark text or browse watermark image
4. Choose anchor and transparency settings
5. Use preview to confirm result
6. Start processing

### 5. Remove Background
AI subject removal runs offline using bundled ONNX Runtime and U2Net. No Python, account or model download is required. The first preview takes longer while the model loads. Inspect fine edges, glass, and images with many separate objects.

Steps:
1. Select `Background`.
2. Choose `Auto removal` for objects/photos, or `Background colour` for plain backgrounds. Colour mode has a 0–100% tolerance slider and editable number; high values can erase the subject.
3. Check preview result carefully
4. Remove unwanted files from queue if needed
5. Start processing when satisfied

## Metadata and Smart rename

- **Metadata:** inspect/search embedded tags and edit title, description, author, copyright, keywords, capture date and camera/software fields. Save as a new PNG, JPEG or WebP. Existing files are never overwritten. PNG/WebP are lossless 8-bit outputs; JPEG is re-encoded and only the first frame is saved. Technical tags are inspected read-only. Optionally remove descriptive metadata while keeping colour profiles.
- **Smart rename:** add files/folders, then preview prefixes/suffixes, kept characters or name parts, find/replace, case and numbering. Export creates renamed copies in a new folder, preserving file contents. Names and collisions are handled safely, with up to 5000 files. Settings are remembered.


## Image Cutout

Click its left navigation button to open the editor directly. Load an image, add/duplicate boxes, drag their edges to resize, and choose Export cutouts. Switching tools preserves your editing work for this session. Ctrl+O loads an image, Ctrl+D duplicates a box, Delete removes the selected box, and Ctrl+Enter exports.

## During Processing

- A progress window appears.
- You can click `Cancel` at any time.

## After Processing
- A completion popup shows success/fail counts.
- Click `View Files` to open the export folder immediately.
