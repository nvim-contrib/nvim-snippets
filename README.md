# nvim-snippets

[![CI](https://github.com/nvim-contrib/nvim-snippets/actions/workflows/ci.yml/badge.svg)](https://github.com/nvim-contrib/nvim-snippets/actions/workflows/ci.yml)
[![Release](https://github.com/nvim-contrib/nvim-snippets/actions/workflows/release.yml/badge.svg)](https://github.com/nvim-contrib/nvim-snippets/actions/workflows/release.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A curated collection of VS Code-compatible snippets for Neovim, covering multiple programming languages and testing frameworks.

## Go

### Ginkgo — Test Structure

| Prefix | Expands to |
|--------|-----------|
| `desc` / `Desc` | `Describe(...)` block |
| `descv` / `Descv` | `var _ = Describe(...)` (top-level suite entry) |
| `desct` / `Desct` | `DescribeTable(...)` with `Entry` |
| `cont` / `Cont` | `Context(...)` block |
| `when` / `When` | `When(...)` block |
| `it` / `It` | `It(...)` test case |
| `by` / `By` | `By(...)` step annotation |

### Ginkgo — Setup & Teardown

| Prefix | Expands to |
|--------|-----------|
| `bef` / `Bef` | `BeforeEach` |
| `befs` / `Befs` | `BeforeSuite` |
| `befa` / `Befa` | `BeforeAll` |
| `aft` / `Aft` | `AfterEach` |
| `afts` / `Afts` | `AfterSuite` |
| `afta` / `Afta` | `AfterAll` |
| `jus` / `Jus` | `JustBeforeEach` |
| `syncbefs` / `Syncbefs` | `SynchronizedBeforeSuite` |
| `syncafts` / `Syncafts` | `SynchronizedAfterSuite` |

### Gomega — Assertions

| Prefix | Expands to |
|--------|-----------|
| `ex` / `Ex` | `Expect(...).To(...)` |
| `exerr` / `Exerr` | `Expect(err).NotTo(HaveOccurred())` |
| `exs` / `Exs` | `Expect(Func()).To(Succeed())` |
| `ev` / `Ev` | `Eventually(...).Should(...)` |
| `evf` / `Evf` | `Eventually(func() ...).Should(...)` |
| `cons` / `Cons` | `Consistently(...).Should(...)` |
| `consf` / `Consf` | `Consistently(func() ...).Should(...)` |
| `Ω` | `Ω(...).Should(...)` |
| `Ωerr` | `Ω(err).ShouldNot(HaveOccurred())` |
| `Ωs` | `Ω(Func()).Should(Succeed())` |

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
