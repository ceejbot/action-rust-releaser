# action-rust-releaser

This is ceejbot's action for releasing Rust tools to a personal homebrew tap. It encodes a number of personal opinions about that release workflow, but who knows? You might find it useful too.

Usage:

```yaml
jobs:
    release:
        name: release
        runs-on: ubuntu-latest
        steps:
            - uses: ceejbot/actions-rust-releaser@v1
              with:
                  executable: codefact
                  refname: ${{ github.ref_name }}
                  tap_repo: ceejbot/homebrew-tap
                  tap_email: robot@example.com
                  tap_user: "🍺🤖"
```

You should pin to the full-length hash for the most recent commit when you start using this action. This is the safest way to know what code you're running.

## LICENSE

This code is licensed via [the Parity Public License.](https://paritylicense.com) This license requires people and companies who build on top of this source code to share their work with the community, too. See the license text for details.
