# simple-sqlfluff.nvim
A dead-simple batteries-included sqlfluff linter for Neovim.

![Logo](./repo/images/simple-sqlfluff-logo.png)


# 📎 Requirements
- Tested on Neovim 0.11.0.
- [sqlfluff](https://docs.sqlfluff.com/en/stable/index.html) (Tested on v3.4.0)

# 💾 Installation
## Lazy
```lua
{
    "michhernand/simple-sqlfluff.nvim",
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
}
```

# ⚙️ Configuration
For configuring sqlfluff, use one of [sqlfluff's configuration file formats](https://docs.sqlfluff.com/en/stable/configuration/setting_configuration.html#configuration-files).
