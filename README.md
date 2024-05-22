# [none-ls-external-sources](https://github.com/Zeioth/none-ls-external-sources.nvim)
All external sources not natively supported by none-ls.

<div align="center">
  <a href="https://discord.gg/ymcMaSnq7d" rel="nofollow">
      <img src="https://img.shields.io/discord/1121138836525813760?color=azure&labelColor=6DC2A4&logo=discord&logoColor=black&label=Join the discord server&style=for-the-badge" data-canonical-src="https://img.shields.io/discord/1121138836525813760">
    </a>
</div>

## Table of contents

- [Why](#why)
- [How to install](#how-to-install)
- [How to use none-ls external sources](#how-to-use-none-ls-external-sources)
- [How to contribute](#how-to-contribute)
- [FAQ](#faq)

## Why
**Problem**:
* [none-ls external sources](https://github.com/nvimtools/none-ls-extras.nvim?tab=readme-ov-file#related-projects) are chaotic and often don't follow the directory conventions of none-ls, nor the package names provided by mason, making impossible for package loaders to load them correctly.

**Solution**:
* By having all external sources in a single place, we can ensure a minimum level of quality and compatibility.

## How to install

```lua
{
  "zeioth/none-ls-autoload.nvim",
  event = "BufEnter",
  dependencies = {
    "williamboman/mason.nvim"
    "zeioth/none-ls-external-sources.nvim"
  },
  opts = {},
},
```
While using [none-ls-autoload](https://github.com/Zeioth/none-ls-autoload.nvim) is not mandatory, it's recommended.

## How to use none-ls external sources
On this example, we are loading all available external sources.

```lua
{
  "zeioth/none-ls-autoload.nvim",
  event = "BufEnter",
  dependencies = {
    "williamboman/mason.nvim",
    "zeioth/none-ls-external-sources.nvim"
  },
  opts = {
    -- Here you can add support for sources not oficially suppored by none-ls.
    external_sources = {
      -- diagnostics
      'none-ls-external-sources.diagnostics.cpplint',
      'none-ls-external-sources.diagnostics.eslint',
      'none-ls-external-sources.diagnostics.eslint_d',
      'none-ls-external-sources.diagnostics.flake8',
      'none-ls-external-sources.diagnostics.luacheck',
      'none-ls-external-sources.diagnostics.psalm',
      'none-ls-external-sources.diagnostics.shellcheck',
      'none-ls-external-sources.diagnostics.yamllint',

      -- formatting
      'none-ls-external-sources.formatting.autopep8',
      'none-ls-external-sources.formatting.beautysh',
      'none-ls-external-sources.formatting.easy-coding-standard',
      'none-ls-external-sources.formatting.eslint',
      'none-ls-external-sources.formatting.eslint_d',
      'none-ls-external-sources.formatting.jq',
      'none-ls-external-sources.formatting.latexindent',
      'none-ls-external-sources.formatting.reformat_gherkin',
      'none-ls-external-sources.formatting.rustfmt',
      'none-ls-external-sources.formatting.standardrb',
      'none-ls-external-sources.formatting.yq',

      -- code actions
      'none-ls-external-sources.code_actions.eslint',
      'none-ls-external-sources.code_actions.eslint_d',
      'none-ls-external-sources.code_actions.shellcheck',
    },
  },
},
```

## How to contribute
You can contribute by sending a pull request with the source you want to add. But in order to be accepted, your source will have to:

* Be in [the right directory](https://github.com/Zeioth/none-ls-external-sources.nvim/tree/main/lua/none-ls-external-sources) (formatting, diagnostics, code_actions)
* Your source file MUST have the same name as its corresponding mason package.
* You must manually test it and ensure it works before sending the PR (sending a screenshot is encouraged).

And finally, it must not be an already supported none-ls [buintin source](https://github.com/nvimtools/none-ls.nvim/tree/main/lua/null-ls/builtins).

## 🌟 Support the project
If you want to help me, please star this repository to increase the visibility of the project.

[![Stargazers over time](https://starchart.cc/Zeioth/none-ls-external-sources.nvim.svg)](https://starchart.cc/Zeioth/none-ls-external-sources.nvim)

## FAQ

* **Will you support this repository forever and ever?** No, of course not.
* **And what can I do if this repository is ever discontinued?** Fork it, and maintain it yourself. As long as you keep the directory structure, you won't break anything.
* **Will you delete old sources?** Yes, once a source stop being available on mason. This contrast with `none-ls`, which delete any source that has not been updated in more than 1 year, leaving many mason packages without support.
* **X source from this repository is not on mason anymore**: Then please open an issue and report it, or ideally send a PR to delete it.

## Related projects

* [none-ls-autoload.nvim](https://github.com/Zeioth/none-ls-autoload.nvim)
