# Contributing

How we work across Blockout Games repositories. Short, because the tooling enforces most of it.

A repository with its own `CONTRIBUTING.md` follows that file instead; every repository's own
`README.md` says how to set it up and which checks to run.

> [!NOTE]
> Our repositories are private and we do not take unsolicited outside contributions. Found a
> security problem? Follow the [security policy](https://github.com/BlockoutGames/.github/blob/main/SECURITY.md). Want to work with us? Get in touch
> through [www.blockoutgames.com](https://www.blockoutgames.com).

## What to work on

Each repository keeps its board in its docs vault (`docs/Board.md` or `vault/Board.md`). Take a
card from **Next**, move it to **In progress**, and say what is true when it is done. Anyone can
add to **Backlog**.

## Branches

`main` is always releasable and always green. Nobody commits to it directly: a direct push is
refused, for everyone.

Work on a branch named `type/short-name`, using the commit types below:

```text
feat/map-voting
fix/double-grant-on-rejoin
docs/onboarding
```

Keep a branch to one change. Two changes in one pull request take longer to review than two pull
requests.

## Commits

```text
type(scope): what changed, in the imperative, lowercase

feat(shop): show the price in the player's currency
fix(save): keep the last session when a write fails
docs(admin): list the moderation commands
```

| Type       | For                                                     |
| ---------- | ------------------------------------------------------- |
| `feat`     | Something new for a player or a developer               |
| `fix`      | Something wrong put right                               |
| `balance`  | A tuned number in game config, no new behaviour (games) |
| `docs`     | Documentation only                                      |
| `test`     | Tests only                                              |
| `refactor` | Code moved or reshaped, behaviour unchanged             |
| `perf`     | Faster or lighter, behaviour unchanged                  |
| `build`    | Dependencies, build tooling                             |
| `ci`       | The workflows                                           |
| `chore`    | Anything else that is not product code                  |

The scope is optional: a service, a package, an app or a feature. A `!` after the type marks a
change that breaks something others depend on, such as a save-format change (`feat(data)!:`).

The commit-message hook checks the first line. The body is free text: say why, not what.

## Pull requests

- **Fill in the template.** What changes, why, and how a reviewer can see it working.
- **The title follows the commit format.** Every merge is a squash, so the title becomes the commit
  on `main` and the line in the changelog. A workflow checks it.
- **Keep it small.** Under 400 lines changed is easy to review; a very large pull request is sent
  back to be split.
- **Run the checks first.** `lune run check` in a game, `pnpm check` in the platform. CI runs the
  same thing, and a red check is not merged.
- **Show it in Studio.** Anything visual, physical or to do with purchases gets numbered steps a
  reviewer can follow in under five minutes.
- **One approval**, then the author merges once every check is green. The branch is deleted on merge.

Labels are applied by a workflow from the paths and the title; the only one set by hand is
`blocked`.

## The rules that do not bend

> **The server decides.** A client asks for an action; the server checks it and applies it. Never
> trust a client for currency, damage, ownership, prices, positions or time.

> **Secrets never live in files.** Keys belong in GitHub environments or your local `.env`, which
> is never committed.

> **"Powered by Blockout Games" stays.** Every game built on the template keeps the attribution on
> its loading screen. See the template's `LICENSE.md`.

## Coding agents

Agents follow the repository's `AGENTS.md`, work on a card a person points them at, and commit as
the person running them. A person owns every outcome. Agents never upload assets or publish places.

## Conduct

Everyone working with us follows the [code of conduct](https://github.com/BlockoutGames/.github/blob/main/CODE_OF_CONDUCT.md).
