# Hinode Module - Compatibility

<!-- Tagline -->
<p align="center">
    <b>A Hugo module to add backwards compability with Hugo &lt;0.141.0 to your Hinode site</b>
    <br />
</p>

<!-- Badges -->
<p align="center">
    <a href="https://gohugo.io" alt="Hugo website">
        <img src="https://img.shields.io/badge/generator-hugo-brightgreen">
    </a>
    <a href="https://gethinode.com" alt="Hinode theme">
        <img src="https://img.shields.io/badge/theme-hinode-blue">
    </a>
    <a href="https://github.com/gethinode/mod-compatibility/commits/main" alt="Last commit">
        <img src="https://img.shields.io/github/last-commit/gethinode/mod-compatibility.svg">
    </a>
    <a href="https://github.com/gethinode/mod-compatibility/issues" alt="Issues">
        <img src="https://img.shields.io/github/issues/gethinode/mod-compatibility.svg">
    </a>
    <a href="https://github.com/gethinode/mod-compatibility/pulls" alt="Pulls">
        <img src="https://img.shields.io/github/issues-pr-raw/gethinode/mod-compatibility.svg">
    </a>
    <a href="https://github.com/gethinode/mod-compatibility/blob/main/LICENSE" alt="License">
        <img src="https://img.shields.io/github/license/gethinode/mod-compatibility">
    </a>
</p>

## About

![Logo](https://raw.githubusercontent.com/gethinode/hinode/main/static/img/logo.png)

> [!CAUTION]
> Use this module only when using Hinode [v0.28.2](https://github.com/gethinode/hinode/releases/tag/v0.28.2) or later in combination with Hugo <[v0.141.0](https://github.com/gohugoio/hugo/releases/tag/v0.141.0).

Hinode is a clean blog theme for [Hugo][hugo], an open-source static site generator. Hinode is available as a [template][repository_template], and a [main theme][repository]. Hugo [v0.141.0](https://github.com/gohugoio/hugo/releases/tag/v0.141.0) introduced a new [try](https://gohugo.io/functions/go-template/try/) mechanism to improve error handling. This is a breaking change with older Hugo versions.

This module includes several partials and render hooks to improve compatibility with Hinode sites that are still using an older Hugo version. Specifically, this module was introduced to ensure Hinode is compatible with CloudCannon's [Bookshop](https://github.com/CloudCannon/bookshop) component framework. The [embedded Hugo renderer](https://github.com/CloudCannon/bookshop/releases/tag/v3.11.0) still uses Hugo v0.136.1 under the hood.

## Contributing

This module uses [semantic-release][semantic-release] to automate the release of new versions. The package uses `husky` and `commitlint` to ensure commit messages adhere to the [Conventional Commits][conventionalcommits] specification. You can run `npx git-cz` from the terminal to help prepare the commit message.

## Configuration

Mount this module first in the site's module configuration to replace Hinode's partials and render hooks that are incompatible with Hugo &lt;v0.141.0. The following module configuration is an example (define the configuration in e.g. `hugo.toml`).

```toml
[module]
  [module.hugoVersion]
    extended = true
    min = "0.120.0"
    max = "0.140.2"
  [[module.imports]]
    path = "github.com/gethinode/mod-compatibility"
  [[module.imports]]
    path = "github.com/gethinode/hinode"
```

<!-- MARKDOWN LINKS -->
[hugo]: https://gohugo.io
[hinode_docs]: https://gethinode.com
[repository]: https://github.com/gethinode/hinode.git
[repository_template]: https://github.com/gethinode/template.git
[conventionalcommits]: https://www.conventionalcommits.org
[husky]: https://typicode.github.io/husky/
[semantic-release]: https://semantic-release.gitbook.io/
