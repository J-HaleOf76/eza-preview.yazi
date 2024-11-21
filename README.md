# eza-preview.yazi

[Yazi](https://github.com/sxyazi/yazi) plugin to preview directories using [eza](https://github.com/eza-community/eza), can be switched between list and tree modes.

List mode:
![list.png](list.png)

Tree mode:
![tree.png](tree.png)

## Requirements

- [yazi](https://github.com/sxyazi/yazi)
- [eza](https://github.com/eza-community/eza)

## Installation

### Linux/MacOS

```sh
git clone https://github.com/sharklasers996/eza-preview.yazi ~/.config/yazi/plugins/eza-preview.yazi
```

## Usage

Add `eza-preview` to previewers in `yazi.toml`:

```toml
[[plugin.prepend_previewers]]
name = "*/"
run = "eza-preview"
```

Set key binding to switch between list and tree modes in `keymap.toml`:

```toml
[manager]
prepend_keymap = [
  { on = [ "E" ], run = "plugin eza-preview",  desc = "Toggle tree/list dir preview" },
  { on = [ "-" ], run = "plugin eza-preview --args='inc-level'", desc = "Increment tree level" },
  { on = [ "_" ], run = "plugin eza-preview --args='dec-level'", desc = "Decrement tree level" },
]
```

List mode is the default, if you want to have tree mode instead when starting yazi - update `init.lua` with:

```lua
require("eza-preview"):setup{
  level = 2 -- default level: 3
}
```
