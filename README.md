## 🤖 Midjourney Bot Prompt Guide (2,505 tokens)

Designed for LLM agents to craft midjourney prompts from user input.

## text prompt construction

a combination of objects, attributes, emotions, verbs by [name of artist], [type of composition] composition, [types of artistic moods], [types of artistic quality], [types of artistic techiques], [types of artistic styles], [types of artistic medium] 

## Image Prompts

- Influence a job's composition, style, and colors using image prompts.
- Combine with text prompts or use alone.
- Add image prompts via direct online image URLs ending in `.png`, `.gif`, `.webp`, `.jpg`, or `.jpeg`.

### Guidelines:
- Place image prompts at the start.
- Must have either two images or one image and text.
- Obtain image URL by right-clicking and selecting "Copy Image Address".
- Mobile users can use `/blend` for a simplified process.

### Uploading Images on Discord:
1. Send the image to the Midjourney Bot.
2. Obtain the link:
   - **Desktop**: Right-click -> "Copy Link".
   - **Web**: Expand image -> Right-click -> "Copy image address".
   - **Mobile**: Tap and hold -> "Copy Media Link".
   - Alternatively, "Open in Browser" to get the URL.

### Privacy:
- Send images via DM to Midjourney Bot for privacy.
- Image prompts are public on Midjourney unless in Stealth Mode.

### Tips:
- Crop images to match final aspect ratio.
- Use `--iw` to adjust image vs. text weight.
  - Default: 1
  - Range: 0–2 (Vary by model version)

### Example:
`/imagine prompt flowers.jpg birthday cake --iw .5`

### Technical:
- Image-only prompts aren't compatible with `--stylize` or `--weird`.

## Parameters for Image Generation

- **Parameters**: Options added to prompts affecting image generation. Always added at the end.
- **Example**: `/imagine a vibrant California poppy --aspect 23 --stop 95 --no sky`
- **Note for Apple Users**: Apple might change `--` to `—`. Both are accepted.

### Basic Parameters:

1. **Aspect Ratios**
   - `--aspect` or `--ar`: Change the aspect ratio.
2. **Chaos**
   - `--chaos <0-100>`: Variability in results. Higher values = more unusual outputs.
3. **Fast**
   - `--fast`: Use Fast Mode.
4. **Image Weight**
   - `--iw <0-2>`: Sets image prompt weight. Default is 1.
5. **No**
   - `--no`: Negative prompting, e.g., `--no plants` removes plants.
6. **Quality**
   - `--quality` or `--q <.25, .5, or 1>`: Rendering quality. Default is 1.
7. **Relax**
   - `--relax`: Use Relax Mode (only available in some plans).
8. **Repeat**
   - `--repeat` or `--r <1-40>`: Re-run a job multiple times.
9. **Seed**
   - `--seed <0-4294967295>`: Seed number for initial image grids. Using the same seed = similar images.
10. **Stop**
   - `--stop <10-100>`: Stop a job partway. Earlier stops = blurrier results.
11. **Style**
   - `--style`: Switch between Midjourney Model versions or Niji Model versions.
   - version 5.2 is only compatible with the following values for --style: raw
12. **Stylize**
   - `--stylize` or `--s <number>`: Strength of Midjourney's aesthetic style.
13. **Tile**
   - `--tile`: Create repeating tiles for seamless patterns.
14. **Turbo**
   - `--turbo`: Use Turbo Mode.
15. **Weird**
   - `--weird` or `--w <0-3000>`: Explore unusual aesthetics.

### Default Values (Model Version 5, 5.1, and 5.2):

- **Aspect Ratio**: 1:1
- **Chaos**: 0 (0-100)
- **Quality**: 1 (.25, .5, or 1)
- **Seed**: Random (0-4294967295)
- **Stop**: 100 (10-100)
- **Stylize**: 100 (0-1000)

## Multi Prompts with Midjourney Bot

- Use `::` to blend multiple concepts. 
  - **Example**: `space:: ship` blends 'space' and 'ship'.
  - No spaces between `::`.
- Multi-prompts supported in Model Versions: `1, 2, 3, 4, 5, niji, niji 5`.

### Basics:
- `space ship` → Image of a sci-fi spaceship.
- `space:: ship` → Sailing ship in space.
- `cheese cake painting` → Painted cheesecake.
- `cheese:: cake painting` → Painted cakes of cheese.
- `cheese:: cake:: painting` → Cakes with cheese and classic painting elements.

### Prompt Weights:
- Assign importance using numbers after `::`.
  - **Example**: `space::2 ship` emphasizes 'space' more than 'ship'.
- Only Models `4, niji 4, niji 5, 5, 5.1, 5.2` accept decimals for weights.
- Default weight: `1`.
- Weights are normalized. **Examples**:
  - `space:: ship` = `space::1 ship` = `space::2 ship::2`.
  - `cheese::2 cake` = `cheese::4 cake::2`.

### Negative Prompt Weights:
- Use negative weights to reduce unwanted elements.
  - Sum of weights must be positive.

### `--no` Parameter:
- Equal to `-0.5` weight.
  - **Example**: `vibrant tulip fields:: red::-.5` = `vibrant tulip fields --no red`.

