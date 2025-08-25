# Thaumcraft Research Helper — Web Tool for Thaumcraft 4 Research

[![Releases](https://img.shields.io/badge/Releases-Download-blue?logo=github)](https://github.com/hammamkaremo/thaumcraft-research-helper/releases)  
https://github.com/hammamkaremo/thaumcraft-research-helper/releases

[![HTML5](https://img.shields.io/badge/HTML5-Ready-orange?logo=html5)](https://github.com/hammamkaremo/thaumcraft-research-helper/releases) [![Minecraft](https://img.shields.io/badge/Minecraft-Tools-green?logo=minecraft)](https://github.com/hammamkaremo/thaumcraft-research-helper/releases)

A simple, web-based research helper for older versions of Thaumcraft. This tool helps you plan and track research in Thaumcraft 4. It runs in any modern browser. Download the release and run the site locally or host it on any static web host.

Table of contents
- About
- Features
- Screenshots and visual guide
- Quick start (download & run)
- Run manually (file execution)
- Browser hosting options
- Interface walkthrough
- Research system primer (Thaumcraft 4)
- Research example walkthroughs
- Dataset and formats
- Keyboard controls & shortcuts
- Accessibility & themes
- Advanced tips and workflows
- Integrations and export
- Development setup
- Contribution guide
- Testing and QA
- Changelog
- License
- Credits
- FAQ

About
This web tool aims to speed up Thaumcraft research. It shows aspects, notes required discoveries, and suggests research paths. You can log research attempts, track progress, and print cheat sheets. It keeps data local in your browser. You can export and import your research lists.

Features
- Fast, offline-friendly web app.
- Aspect browser with search and filters.
- Research table with requirements and steps.
- Research node planner with drag and drop.
- Auto-suggest research hints based on available aspects.
- Save and load research sessions as JSON.
- Export printable research sheets.
- Compact UI for tablets and desktops.
- No server required for local use.
- Works with TC4 research mechanics and common add-ons data.

Screenshots and visual guide
![Alchemical Circle](https://i.imgur.com/3u7QwYb.png)  
![Research Grid](https://i.imgur.com/LxXf2kM.png)

These images show mockups and UI examples. They use minecraft-themed art to match the theme. The UI uses clean icons and focused color contrast to make the research flow clear.

Quick start (download & run)
Download the release file and execute it. Get the release from:
https://github.com/hammamkaremo/thaumcraft-research-helper/releases

Steps
1. Visit the releases link above.
2. Download the zip file for the latest release. The file name will look like thaumcraft-research-helper-vX.Y.zip or similar.
3. Extract the zip to a folder.
4. Open index.html in your browser, or run a simple local server as shown below.

The release file contains the full web app bundle. You need to download that file and run it. The app is static and runs in the browser.

Run manually (file execution)
The app uses static files: HTML, CSS, JS, and assets. You can open index.html directly in your browser. For a better experience, run a local server.

Run with Python (recommended)
- Python 3: open a terminal in the extracted folder.
- Run: python -m http.server 8000
- Open: http://localhost:8000

Run with Node (http-server)
- Install: npm i -g http-server
- Start: http-server -p 8000
- Open: http://localhost:8000

Run with other tools
- Use any static file server.
- Place the release files on GitHub Pages, Netlify, or Vercel.
- Host the extracted folder on your web host.

Browser hosting options
- GitHub Pages: push the built files to gh-pages branch or to the docs folder.
- Netlify: drag and drop the extracted folder.
- Vercel: point to the folder or repository.
- Local: use any static server to serve the files.

Interface walkthrough
Main layout
- Header: project title, version badge, quick load/save.
- Left column: Aspect list and search.
- Middle area: Research board (nodes and layout).
- Right column: Research details, steps, and logs.

Aspect list
- Search by name.
- Filter by primal aspect.
- Click an aspect to add it to a research slot.
- Drag aspects to combine them in the research grid.

Research board
- Nodes represent research entries.
- Each node shows required aspects and research level.
- Drag nodes to reorder your research queue.
- Lock nodes to keep them in place.

Research details
- Shows steps to unlock a research.
- Shows required items and notes.
- Shows alternative aspect paths if available.

Session management
- Save current session as a JSON file.
- Load a session from disk.
- Export printable research sheets as PDF from your browser.

Research system primer (Thaumcraft 4)
This section explains the research mechanics used in Thaumcraft 4. The app models these elements. If you know the mod, this will align with common TC4 setups. If you prefer a refresher, read the primer.

Aspects
- Aspects are elemental properties.
- Some are primal: Aer, Terra, Ignis, Aqua, Ordo, Perditio.
- Others combine two or more aspects into a compound aspect.
- Aspects combine based on recipes and discovered items.

Research pages
- A research entry contains pages.
- Pages show text, diagrams, recipes, and discovery requirements.
- Some pages require scanning of items with a Thaumometer.
- Some pages require crafting or infusion.

Research notes
- Research notes record your discoveries.
- Notes show which aspects you used.
- The helper tracks these notes and links them to research entries.

Research nodes and meta
- A research node groups a set of related entries.
- Nodes can depend on other nodes.
- Completing one node can unlock branches.
- The app models node dependencies for planning.

Research devices
- Thaumonomicon is your main reference.
- Research table and infusion altar serve different research types.
- The helper separates table-based research from infusion-based research.

Infusion mechanics (brief)
- Infusion requires placing items around an altar.
- It consumes flux on failure.
- The app lists common infusion setups and required items.

Example: discovering an item
- Scan an item to learn its basic aspects.
- Use aspects to form a research recipe.
- Open the research entry and complete the steps.

Research example walkthroughs
The app includes sample entries to practice. Below are extended step-by-step guides that you can follow with the helper.

Example 1 — Simple research: "Warded Leather"
1. Open the app.
2. Find "Warded Leather" in the research list.
3. Read the requirements. This entry needs Terra and Victus aspects.
4. Prepare items: leather, thread, and a clavicula.
5. Mark the entry done in the planner.
6. The app updates your research progress.

Example 2 — Infusion: "Arcane Lens"
1. Select the node for "Arcane Lens".
2. The helper shows required aspects and item placement hints.
3. Drag the items from your inventory list into the sample slot.
4. Use the helper to verify aspect totals.
5. The helper highlights weak points where you lack aspects.
6. Adjust the items and re-check until the totals match.
7. Mark the infusion as planned.

Example 3 — Multi-node chain planning
1. Pick a high-level research you want.
2. Use the planner to add all required prerequisite nodes.
3. Use drag-and-drop to arrange the nodes in an order that matches your play session.
4. Export the plan to JSON.
5. Share the JSON with friends or keep it for reference.

Dataset and formats
Data model
- Items: id, name, aspects, tags.
- Aspects: id, name, symbol, parents.
- Research entries: id, title, node, pages, requirements, notes.
- Nodes: id, title, dependencies, children.
- Sessions: saved nodes, saved positions, user metadata.

JSON schema
- The app uses a compact JSON schema for sessions.
- Keys are short to keep file sizes small.
- Example structure:
  {
    "meta": { "version": "1.0.0", "date": "2025-08-01" },
    "aspects": { "Aer": { "amount": 10 }, "Ignis": { "amount": 5 } },
    "nodes": [ { "id": "arc-lens", "status": "planned" } ],
    "layout": [ { "id": "arc-lens", "x": 100, "y": 200 } ]
  }

Export formats
- JSON: full session export and import.
- CSV: flat list of nodes and requirements.
- PDF: printable sheet from the browser print dialog.

Keyboard controls & shortcuts
- G: toggle grid snap on the research board.
- S: save session.
- L: load session.
- F: search aspects.
- Arrow keys: nudge selected node.
- Space: toggle play/pause for animated guides.

Accessibility & themes
Color themes
- Default: dark mode with parchment textures.
- Light: high contrast, minimal texture.
- Colorblind-friendly: distinct color palette for aspects.

High contrast mode
- Toggle high contrast to enhance readability.
- The app uses large fonts and clear icons in this mode.

Screen reader support
- The app partially supports screen readers.
- All main buttons have aria-label.
- The board uses simple DOM elements for better navigation.

Advanced tips and workflows
Plan for multiple players
- Export a plan and share the JSON file.
- Each player can load the plan and mark nodes as done.
- Use the export to coordinate who will tackle infusion steps.

Batch printing
- Use the print export to create physical cheat sheets.
- Print the aspect totals and the item lists for quick reference.

Custom research entries
- The app lets you add custom research entries.
- Fill in title, aspects, pages, and dependencies.
- Save and export your custom set as JSON.

Data merging
- Merge session data by importing multiple JSON files.
- The app will combine nodes and keep unique IDs.
- Resolve conflicts by choosing the most recent timestamp.

Integrations and export
Integration ideas
- Link to a modpack manifest to auto-load items.
- Export to a wiki format for community pages.
- Connect to a cloud storage provider to sync sessions.

API format
- The export JSON is API-friendly.
- External tools can parse the session JSON and generate planners or wiki pages.

Third-party scripts
- Use simple Node scripts to batch convert mod data into the app schema.
- Example: a script that turns a mod's aspect list into the app's JSON.

Development setup
This project uses HTML5, CSS, and vanilla JS for the core. You can run and develop it with basic tools.

Prereqs
- Node.js (for building and dev tools)
- A modern browser
- Git

Clone the repo
git clone https://github.com/hammamkaremo/thaumcraft-research-helper.git
cd thaumcraft-research-helper

Install
- Run npm install to install dev tools.
- The app uses simple build steps for bundling and linting.

Build
- npm run build to create a production bundle.
- The built files end up in the dist folder.
- The dist folder contents are what the release zip contains.

Dev server
- npm run dev starts a development server with live reload.
- Open http://localhost:3000

Testing
- This project includes unit tests for core logic.
- Run npm test to run the test suite.
- The test suite checks aspect math, node merging, and export/import.

Code style
- The project uses ESLint with a simple rule set.
- Use Prettier for formatting.
- Keep functions small and pure.

Contribution guide
How to contribute
- Fork the repo.
- Create a feature branch.
- Write tests for new logic.
- Open a pull request with a clear description.

Issue reporting
- Create issues for bugs or feature requests.
- Include steps to reproduce and expected behavior.
- Attach session JSON files when relevant.

Feature requests
- Label ideas with enhancement.
- Small, incremental changes get review faster.
- Provide UI mockups for new panels or workflows.

Code review checklist
- Keep changes focused.
- Keep the UI accessible.
- Maintain JSON schema compatibility.
- Update the changelog when adding a release-worthy feature.

Testing and QA
Unit tests
- Test the aspect math thoroughly.
- Test combination logic for compound aspects.
- Test export/import for edge cases.

Manual QA
- Run the app in several browsers.
- Test local file loading and saving.
- Test drag-and-drop on different screen sizes.

Performance
- The app keeps nodes in a lightweight array.
- Avoid heavy DOM operations in large sessions.
- Use virtualization if sessions exceed 500 nodes.

Changelog
v1.0.0 — Initial release
- Core research planner.
- Aspect browser and search.
- Save/load session.
- Export to JSON and printable sheets.

v1.1.0 — UI polish
- Improved aspects filter.
- Better keyboard navigation.
- New color themes.

v1.2.0 — Infusion planner
- Infusion layout helper.
- Item placement hints.
- Aspect totals and warnings.

Future plans
- Team sync and cloud save.
- Plugin support to load modpacks.
- Deeper integration with Thaumonomicon data files.

License
This project uses the MIT license. See the LICENSE file in the release bundle for details.

Credits
- Project lead: Hammam Karemo (original repo owner).
- UI mockups: community artists and players.
- Icons: public domain or appropriately licensed sets.
- Thanks to the Thaumcraft modding community for research mechanics documentation.

Resources and links
- Release page (download and run the file from here):  
  https://github.com/hammamkaremo/thaumcraft-research-helper/releases
- Thaumcraft 4 mod wiki and community pages.
- Minecraft texture reference pages.

Design assets
- Parchment texture: public domain textures from texture libraries.
- Aspect symbols: simplified symbols modeled on TC4 style.

Common questions (FAQ)
Q: How do I get the app running if index.html does not load?
A: Serve the extracted release folder with a static server. Python and http-server work well.

Q: Can I run this on a phone?
A: Yes. The UI adapts but the desktop layout works best for large boards.

Q: How do I add a custom aspect or a new mod item?
A: Use the custom entry form in the settings. Export the session and save the file for reuse.

Q: Does the app modify my Minecraft save?
A: No. The app keeps data local in your browser. You can export and import session files.

Q: Where do I report a bug?
A: Open an issue in the GitHub repository. Include session exports and steps to reproduce.

Security and privacy
- The app runs in your browser. It does not upload data by default.
- Saved session files only live on your device unless you choose to share them.

Typography and icons
- The UI uses system fonts for speed.
- Icons use SVG for sharp rendering.
- Aspect symbols scale cleanly with screen size.

Print layout tips
- Use landscape mode for wide boards.
- Hide the left and right columns via the sidebar toggle to create a compact print sheet.
- Use browser print preview to adjust margins.

Localization
- The app supports basic English text.
- The data schema allows for translations.
- Add localized strings by editing the i18n JSON file.

Backup and migration
- Export sessions before upgrading major versions.
- The app keeps version metadata in the export.
- When opening older exports, the app will attempt safe migration.

Common workflows
Single player speed run
- Add your end-game research.
- Use the planner to expand prerequisites.
- Print a cheat sheet and place it near your crafting area.

Multiplayer team planning
- Export a plan.
- Assign nodes to players by adding a player tag.
- Share the JSON file with the group.

Minimalist play
- Use only the aspect browser.
- Plan one node at a time.
- Keep saved sessions as quick references.

Testing data and examples
The release includes example sessions for training:
- starter-session.json
- midgame-plan.json
- infusion-examples.json

These show common node chains and how to set up infusion patterns.

Asset credits and legal
- Where possible the app uses public domain assets.
- Icons use permissive licenses.
- If you spot a copyrighted image in the release, open an issue and include the image URL.

Release download reminder
Visit the releases page and download the release file. Then extract and run the included index.html or start a static server:
https://github.com/hammamkaremo/thaumcraft-research-helper/releases

Appendix: in-depth research concepts used by the app
The app models several common concepts from Thaumcraft 4. Below are concise, clear descriptions you can use while planning.

1. Aspect composition
- Two aspects can combine to form a third.
- The app calculates derived aspects when you add item scans.
- Use the aspect breakdown tool to see which items yield desired totals.

2. Research node dependency
- Nodes may require other nodes.
- You cannot complete a node if prerequisites are incomplete.
- The planner shows a directed graph of dependencies.

3. Page types
- Text page: lore and hints.
- Recipe page: shows crafting or infusion steps.
- Scan page: requires scanning a specific item.
- Puzzle page: requires combining aspects in a pattern.

4. Infusion risk and stability
- Infusion requires stability around the altar.
- The app lists items that help stabilize or increase stability.
- Calculate risk by comparing required aspects to available totals.

5. Item tags and groups
- Items can carry tags for easy grouping.
- Use tags to find all leather variants or all lenses quickly.

6. Research priority and scheduling
- Mark nodes as high, medium, or low priority.
- Use the scheduler to group similar tasks in one session.

7. Resource planning
- Export item lists for a session.
- Use the list to gather items in your base before starting the research.

8. Aspect farming
- The app suggests easy items to farm for common aspects.
- It lists small farms and drops that yield the aspects you need.

9. Cross-mod items
- The app can import additional item lists.
- Map cross-mod items to equivalent aspects by editing the item entry.

Final notes
This README covers the tool, download steps, run options, and detailed usage. For the release download, get the file from the releases page and run it locally. The releases page contains zipped builds and the index.html needed to run the app:
https://github.com/hammamkaremo/thaumcraft-research-helper/releases

If you want to dive into the code, follow the development setup and open a pull request with tests. Thank you to everyone who tests and improves the tool.