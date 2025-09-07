# Codenames and Such

> *Generic Codename Engine Book*

**Codenames and Such** is an unofficial book for
[Codename Engine](https://codename-engine.com) that details certain development
practices, as well as tips and tricks.

> [!NOTE]
> While the book is complete in terms of pages, ontributions are welcomed under
> the [terms below](#contributing).

## Compiling

> [!NOTE]
> [Nix](https://nixos.org/) users have a basic development shell configuration
> available that loads [mdBook](https://rust-lang.github.io/mdBook/) for use.
> If you are using a Nix shell, then skip to [Opening a
> Server](#opening-a-server).

Install [mdBook](https://rust-lang.github.io/mdBook/). This is the main
program for displaying the book, and provides features such as compiling the
book, opening a hot-reload-supporting web server for the book, and more.

### Highlight.js

For reference: Codenames and Such uses a custom build of
[Highlight.js](https://highlightjs.org/), downloaded from the website, that
includes Haxe syntax highlighting. While it's already included in the
repository under `themes/highlight.js` and is already standardized in mdBook,
it's worth a mention.

### Opening a Server

Use the following mdBook subcommand:

```sh
mdbook serve --open
```

This will compile the book, create a local web server, and open the contents
of the web server in your browser.

## Contributing

Some knowledge of [mdBook](https://rust-lang.github.io/mdBook/) is required in
particular cases. However, for simply editing pages, all you need to know is
how to edit [CommonMark](https://commonmark.org/), along with using the
mdBook CLI tool to preview your changes. See [this section](#compiling) for
more details.

If you are adding a new page, then please appropriately place it in the
respective directory for that page's section. Make sure to add it to the
section's index, as well as [SUMMARY.md](src/SUMMARY.md), to make sure that
the book renders it properly.

Pull requests should *preferably* have their commits squashed in most cases,
or simply just comprise of one commit. However, this is not necessary for most
pull requests.

## License

The book is licensed under the [MIT license](LICENSE).
