# action-rust-releaser

This is ceejbot's action for releasing Rust tools to a personal homebrew tap. It encodes a number of personal opinions about that release workflow, but who knows? You might find it useful too.

Usage:

```yaml
jobs:
    release:
        name: release
        runs-on: macos-latest
        steps:
            - uses: ceejbot/action-rust-releaser@89c36c63bd61c664ce79597d9f8c2f9e22b0bcaa
              env:
                  HOMEBREW_TAP_TOKEN: ${{ secrets.HOMEBREW_TAP_TOKEN }}
                  REPO_TOKEN: ${{ secrets.GITHUB_TOKEN }}
              with:
                  executable: codefact
                  refname: ${{ github.ref_name }}
                  tap_repo: ceejbot/homebrew-tap
                  tap_email: ceejceej@gmail.com
                  tap_user: "🍺🤖"
```

If you use this action, inspect the code, then pin to the full-length hash for the commit you inspected. This is the best way to know what code you're running and that nothing hinky is happening with your secrets.

## Limitations

- At the moment this only builds for Mac ARM & Intel targets. It should build for different sets of targets depending on what host OS it's running on.
- It only knows how to build release assets for a single bin in a crate, while of course there might be more than one.
- It's unsuitable for libraries.

## LICENSE

This code is licensed via [the Parity Public License.](https://paritylicense.com) This license requires people and companies who build on top of this source code to share their work with the community, too. See the license text for details.
