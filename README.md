# YetAnotherSON

A visual Miller-column style editor ideal for deeply nested JSON, with experimental YAML/TOML support. 

A single, self-contained HTML file. No install, no build step, no server — open it in a browser and it works. Runs entirely client-side; your data never leaves the page unless you explicitly save or export it.

## Why this exists

I have been working on a project when i realised that i needed to set up a configuration file for my application in order to make my job easy moving forward.  
Of course JSON first came to mind, *it just works* and i was already using it to store user data.  
However after creating a mockup file i saw that it will end up a mess due to the numerous enties and layers that would be needed.  
So i started researching...magic configuration file formats that supposedly fix all your issues, several commercial and free viewers/editors, discussions arguing which is the best method to use, doing testing with sample data, etc...Only to realise 2 days later that's not the issue at hand here:  

1) **THERE IS NO SINGLE BEST SOLUTION..**.best is what you find easier and more appropriate for your usecase. In my case JSON does everything i need. It only has one issue, and that's a data visualisation/entry problem..which leads us to the next point:
2) **JUST UNNEST YOUR DATA!** It's so obvious! Why i didn't just do this from the start? Because i got deep into this rabbit hole 😁 In my specific case unnesting is *a solution*, just not the *optimal solution*..(because i'll have to be duplicating data)
3) **IT'S SIDE-PROJECT TIME!** Damn it! Guess i'll have to make my own editor with black columns and hookers 🤖😎


Every existing editor style has its own quirks:

- **Tree views** show the full structure but make editing values, or making any structural change across many similar entries, slow and click-heavy.
- **Grid/table views** are great for editing existing values but fall apart the moment you need to add a new field or a new nested object without copy-pasting an entire sibling by hand.
- **Column/"Miller column" browsers** (in the style of macOS Finder, or tools like JSON Hero) get navigation right — one layer per column, nothing flattened, siblings stay visible for comparison — but the ones that exist are read-only viewers, not editors.

Nobody i found had combined the last two: real column-based navigation *with* real structural editing. That gap is what this project fills — every object, array, or plain value gets its own column, one layer of the data at a time, fully editable in place, with the type of each value color-coded and convertible on the fly.

## Features

- Miller-column navigation for arbitrarily nested JSON — click into any object or array to open the next column
- Full inline editing: rename keys, edit values, add/delete/duplicate/reorder properties and items (drag-and-drop, right-click menu, resizable columns)
- Convert any value between String / Number / Boolean / Null / Array / Object, with data preserved wherever the conversion allows it
- Undo/redo, a raw-JSON view with syntax highlighting, and a searchable breadcrumb trail
- Per column filtering; by name, value, or both
- Real file Save / Save As (via the File System Access API where supported), plus JSON/YAML/TOML export
- Fully customizable color palette and light/dark theme, saved and restored as a plain settings file
- Optional experimental YAML/TOML support, lazily loaded from a CDN only when you actually open or save one of those formats — never on startup, never for JSON

## Screenshot

<img width="2060" height="1193" alt="Screenshot 2026-07-13 at 23-23-55 YetAnotherSON — YetAnotherSON" src="https://github.com/user-attachments/assets/789cb220-4fa6-4ba0-834b-de4fc0553d71" />


## Usage

### Just visit **https://st0rm53.github.io/YetAnotherSON/** to launch the editor directly in your browser.

## License

[GNU AGPLv3](https://www.gnu.org/licenses/agpl-3.0.html)

## Author

**St0RM53**

## Links

- Repository: https://github.com/St0RM53/YetAnotherSON
- Issues / feature requests: https://github.com/St0RM53/YetAnotherSON/issues

## Third-party libraries

Optional YAML/TOML support is provided by [js-yaml](https://github.com/nodeca/js-yaml) and [js-toml](https://github.com/sunnyadn/js-toml), both MIT licensed.
