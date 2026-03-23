# Class Manager (Figma Plugin)

A powerful Figma plugin that enables "Class-based" design by treating node trees as reusable, serialized definitions. Save a complex frame once, and re-insert it anywhere in your document or sync it across your team.

![Class Manager UI Preview](https://github.com/user-attachments/assets/placeholder-ui.png)

## Features

- **Deep Serialization**: Captures nested children, auto-layout settings, fills, strokes, effects, and bound variables.
- **Smart Restoration**: Recreates complex node trees with pixel perfection, automatically loading required fonts.
- **Text Style & Variable Support**: Preserves text style references and complex text property variable bindings (font size, letter spacing, etc.).
- **Variable Support**: Preserves variable bindings for colors, spacing, and numbers.
- **Sync & Registry**: Uses Figma's `SharedPluginData` to synchronize class definitions across all users of a document.
- **Local Persistence**: Stores your personal classes in `clientStorage` for use across different files.
- **Group & Search**: Organize your classes with labels and find them instantly with the built-in search.

## Technology Stack

- **Typescript**: Core plugin logic and node manipulation.
- **Vanilla HTML/CSS/JS**: UI implementation with a custom **shadcn/ui** inspired design system.
- **esbuild**: Ultra-fast bundling for plugin distribution.

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18+)
- [npm](https://www.npmjs.com/)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Hakimei/figma-plugin-class-manager.git
   cd create-class-element
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Build the plugin:
   ```bash
   npm run build
   ```

4. In Figma, go to **Plugins** -> **Development** -> **Import plugin from manifest...** and select the `manifest.json` in this folder.

### Development

Run the build in watch mode for a faster development cycle:

```bash
npm run dev
```

## Project Structure

```text
├── .agents/           # AI behavior and skill definitions
├── src/
│   ├── code.ts        # Main plugin sandbox logic (Node API)
│   └── ui.html        # Plugin UI (HTML/CSS/JS)
├── dist/              # Bundled distribution (ignored by git)
├── manifest.json      # Figma plugin manifest
└── build.js           # esbuild build script
```

## Core Workflows

### Saving a Class
1. Select a **Frame**, **Component**, or **Instance** on the Figma canvas.
2. Give it a **Name** (e.g., `Card / Default`) and an optional **Label** for grouping.
3. Click **Save Class**. The node tree is now serialized and stored in the registry.

### Inserting a Class
1. Find the class in the list or use the search bar.
2. Click the class to select it.
3. Click **Insert Selected Class**. The node tree will be recreated at the center of your current viewport.

### Syncing with the Team
Click the **Sync** icon in the header to merge your local classes with the shared registry stored in the Figma file.

## License

MIT
