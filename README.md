# nvim-snippets

[![CI](https://github.com/nvim-contrib/nvim-snippets/actions/workflows/ci.yml/badge.svg)](https://github.com/nvim-contrib/nvim-snippets/actions/workflows/ci.yml)
[![Release](https://github.com/nvim-contrib/nvim-snippets/actions/workflows/release.yml/badge.svg)](https://github.com/nvim-contrib/nvim-snippets/actions/workflows/release.yml)
[![Version](https://img.shields.io/github/v/release/nvim-contrib/nvim-snippets)](https://github.com/nvim-contrib/nvim-snippets/releases/latest)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A curated collection of VS Code-compatible snippets for Neovim, covering multiple programming languages and testing frameworks.

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
