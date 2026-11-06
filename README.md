# Google Engineering Practices, but for agents

A minimal, project-independent starting point for development with Codex: a short
AGENTS.md and local copies of Google's code review and language style guides.

## New project

Select **Use this template → Create a new repository** on GitHub. Clone the new
repository and start Codex there. Add your product code and project-specific CI.

## Existing project

Copy `AGENTS.md`, `docs/google-eng-practices/` and `docs/google-styleguide/` into
your repository. If you already have an AGENTS.md, merge the sections instead of
overwriting your instructions. Preserve the guide paths, licenses and provenance
files. You can give this task directly to your coding agent.

Some upstream style-guide links use published `.html` paths; read the
corresponding `.md` source locally when a generated HTML file is absent. Guides
hosted outside google/styleguide remain external links.

## Enable automatic Codex Code Review

Configure this separately for **each repository**, including repositories created
from this template:

If GitHub is not connected yet, open ChatGPT **Settings → Plugins → GitHub**
and connect your account. Complete the authorization on GitHub, install the
**ChatGPT Codex Connector** for the account or organization that owns the project,
and grant it access to the repository. If it is already installed but the repository
is missing, open [GitHub installed apps](https://github.com/settings/installations),
select **Configure** for ChatGPT Codex Connector, and add the repository under
**Repository access**. Organization installations may require an administrator.

1. Open [Code Review settings](https://chatgpt.com/settings/code-review).
2. Select the repository.
3. Enable **Automatic review**.
4. Set **Review** to **All PRs**.
5. Set **Trigger** to **On every push**.

Open a non-draft PR and verify that Codex starts reviewing automatically. Push a
correction and verify review starts for the new commit too.

See the [official Code Review setup guide](https://learn.chatgpt.com/docs/third-party/github)
for current settings and account requirements. UI labels may vary. If necessary,
`@codex review` requests a manual review; it does not enable automatic reviews.

GitHub's template feature copies files, not Codex integrations or repository rules.
No GitHub Actions workflow, API key or custom review bot is needed for the Codex
integration. Add checks suitable for your project. Where your GitHub plan supports
it, protect the default branch with required checks and approvals. AGENTS.md is
agent guidance, not a substitute for server-enforced merge rules.

## Included material

- [AGENTS.md](AGENTS.md): development workflow, code style and review instructions.
- [Google Engineering Practices](docs/google-eng-practices/README.md): author and reviewer guides.
- [Google Style Guides](docs/google-styleguide/README.md): full tracked upstream repository snapshot.

Each guide directory records its upstream commit in PROVENANCE.md. These are pinned
copies: upstream changes do not arrive automatically. To update, replace the
corresponding snapshot, retain upstream licensing and update its provenance in a PR.
Repositories generated from this template likewise receive no automatic updates.

## License

Original template files use the [MIT License](LICENSE). Vendored Google materials
retain their own licenses; see the LICENSE and provenance files in each guide
directory. The root MIT license does not relicense those materials.
