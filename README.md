# inlinediff-nvim

Simplest Neovim inline diff view with character-level highlighting.

- VS Code-style inline diff view
- Character-level highlighting across the entire buffer width
- Auto-refresh with configurable debounce
- Git-index comparison (works with unsaved buffers)
- Configurable colors

This plugin is solely focused on providing a better inline Git diff view. It is meant to be used alongside your favorite Git plugin (for example, gitsigns). I created inlinediff-nvim because gitsigns lacked character-level highlighting and its inline decorations could disappear on cursor move.

## Install with your favorite plugin manager

```lua
-- lazy.nvim
return {
	"YouSame2/inlinediff-nvim",
    lazy = true, -- disable loading plugin until called with cmd or keys
	return {
		"YouSame2/inlinediff-nvim",
		lazy = true, -- disable loading plugin until called with cmd or keys
		cmd = "InlineDiff",
		opts = {}, -- leave blank to use defaults
		keys = {
			{
				"<leader>ghp",
				function()
					require("inlinediff").toggle()
				end,
				desc = "Toggle inline diff",
			},
		},
	}
```

## Default opts (configure to your liking)

```lua
opts = {
    debounce_time = 200,
    colors = {
        -- context = dim background color; change = bright background color for changed text.
        InlineDiffAddContext = "#182400",
        InlineDiffAddChange = "#395200",
        InlineDiffDeleteContext = "#240004",
        InlineDiffDeleteChange = "#520005",
    },
}
```

## Commands

- `:InlineDiff toggle`
- `:InlineDiff refresh`
