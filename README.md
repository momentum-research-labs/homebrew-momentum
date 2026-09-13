# homebrew-momentum

Homebrew tap for the [Momentum](https://withflywheel.com) CLI.

## Install

**Pending first PyPI publish of `ydderd-momentum-cli`.** The formula’s `url`/`sha256` are
placeholders until `cli/scripts/release.sh` in the monorepo fills them. Until then, install
from git:

```bash
pip install "ydderd-momentum-cli @ git+https://github.com/momentum-research-labs/momentum@main#subdirectory=cli"
```

After the first publish + formula refresh:

```bash
brew install momentum-research-labs/momentum/momentum-cli
momentum auth login --token <fw_cli_…>   # token from a workspace admin
momentum upload ./your-data --scan
```

## Maintaining

`Formula/momentum-cli.rb` is generated/updated by `cli/scripts/release.sh` in the
[momentum](https://github.com/momentum-research-labs/momentum) monorepo after each PyPI publish
(it fills the `url`/`sha256` and regenerates the Python `resource` blocks). Do not retarget
this formula at a legacy `ydderd-flywheel-cli` sdist — that package installs a `flywheel`
binary and will fail the `momentum` test.
