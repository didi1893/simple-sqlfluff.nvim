# simple-sqlfluff.nvim
A dead-simple batteries-included sqlfluff linter for Neovim.

# 📎 Requirements
- Tested on Neovim 0.11.0.
- [sqlfluff](https://docs.sqlfluff.com/en/stable/index.html) (Tested on v3.4.0)

# 💾 Installation
## Lazy
```lua
{
    "michhernand/simple-sqlfluff.nvim",
    keys = {
        { "<leader>Sf", "<cmd>SQLFluffFormat<CR>", desc = "Format w/ SQLFluff" },
        { "<leader>St", "<cmd>SQLFluffToggle<CR>", desc = "Toggle SQLFluff Linting" }
        { "<leader>Se", "<cmd>SQLFluffEnable<CR>", desc = "Enable SQLFluff Linting" }
        { "<leader>Sd", "<cmd>SQLFluffDisable<CR>", desc = "Disable SQLFluff Linting" }
    },
    opts = {}
}
```

## Packer
```lua
use {
    "michhernand/simple-sqlfluff.nvim",
    config = function()
        require("simple-sqlfluff").setup{}
    end,
    keys = function()
        vim.keymap.set("n", "<leader>Sf", "<cmd>SQLFluffFormat<CR>", { desc = "Format w/ SQLFluff" })
        vim.keymap.set("n", "<leader>St", "<cmd>SQLFluffToggle<CR>", { desc = "Toggle SQLFluff Linting" )
        vim.keymap.set("n", "<leader>Se", "<cmd>SQLFluffEnable<CR>", { desc = "Enable SQLFluff Linting" )
        vim.keymap.set("n", "<leader>Sd", "<cmd>SQLFluffDisable<CR>", { desc = "Disable SQLFluff Linting" )
    end
}
```

# ⚙️ Configuration
## Defaults
```lua
opts = {
    autocommands = {
        enabled = true, -- global on/off switch for linting

        -- An array of events to run sqlfluff lint on - if empty, linting is disabled
		events = {
			"BufReadPost",
			"InsertLeave",
		},

        -- An array of file extensions to run sqlfluff lint on - if empty, linting is disabled
		extensions = {
			"*.sql",
		},
    }
}
```
## Configuring SQLFluff
For configuring sqlfluff, use one of [sqlfluff's configuration file formats](https://docs.sqlfluff.com/en/stable/configuration/setting_configuration.html#configuration-files).

# 🖥️ Usage

![Demo1](./repo/gifs/simple-sqlfluff-demo1.gif)

Simply open a `.sql` file and start editing!

Use your preferred method to review linting errors.

*[Trouble](https://github.com/folke/trouble.nvim) (shown in the GIF) provides an excellent interface for reviewing linting (and other) errors.*

## Format File
Default Keybinding: <kbd>leader</kbd>-<kbd>Sf</kbd>

Formats your open buffer per your .sqlfluff settings.

## Toggle Linting
Default Keybinding: <kbd>leader</kbd>-<kbd>St</kbd>

Toggles sqlfluff linting. Turns linting on/off.

## Enable Linting
Default Keybinding: <kbd>leader</kbd>-<kbd>Se</kbd>

Enables sqlfluff linting.

## Disable Linting
Default Keybinding: <kbd>leader</kbd>-<kbd>Sd</kbd>

Disbales sqlfluff linting.
