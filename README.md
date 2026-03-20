# nvim-snippets

> A curated collection of VS Code-compatible snippets for Neovim, covering multiple programming languages and testing frameworks.

[![test](https://github.com/nvim-contrib/nvim-snippets/actions/workflows/ci.yml/badge.svg)](https://github.com/nvim-contrib/nvim-snippets/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/v/release/nvim-contrib/nvim-snippets?include_prereleases)](https://github.com/nvim-contrib/nvim-snippets/releases)
[![License](https://img.shields.io/github/license/nvim-contrib/nvim-snippets)](LICENSE)
[![Neovim](https://img.shields.io/badge/Neovim-0.9%2B-blueviolet?logo=neovim&logoColor=white)](https://neovim.io)

## Snippets

| Language | Frameworks |
|----------|-----------|
| [Go](snippets/go/) | Ginkgo, Gomega |

## Installation

Snippets are distributed in VS Code format and load via [LuaSnip](https://github.com/L3MON4D3/LuaSnip).

### lazy.nvim (standalone)

```lua
{
  "L3MON4D3/LuaSnip",
  dependencies = {
    "nvim-contrib/nvim-snippets",
  },
  config = function()
    require("luasnip.loaders.from_vscode").lazy_load {
      paths = { vim.fn.stdpath("data") .. "/lazy/nvim-snippets" },
    }
  end,
}
```

### AstroNvim

```lua
{
  "L3MON4D3/LuaSnip",
  dependencies = {
    "nvim-contrib/nvim-snippets",
  },
  config = function(plugin, opts)
    -- include the default AstroNvim LuaSnip config
    require("astronvim.plugins.configs.luasnip")(plugin, opts)
    -- load nvim-snippets snippets
    require("luasnip.loaders.from_vscode").lazy_load {
      paths = { vim.fn.stdpath("data") .. "/lazy/nvim-snippets" },
    }
  end,
}
```

## Contributing

Contributions are welcome! To add or improve snippets:

1. Fork the repository
2. Edit or add files under `snippets/<language>/`
3. Run `make validate` to check JSON validity
4. Open a pull request

Snippets follow the [VS Code snippet format](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_snippet-syntax).

## License

MIT — see [LICENSE](LICENSE).
