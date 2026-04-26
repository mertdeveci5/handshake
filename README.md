# Handshake

Handshake is an Agent Skill for stress-testing software plans before implementation.

It makes the agent interview the user relentlessly, one question at a time, about a plan, design, architecture, migration, or feature idea until there is shared understanding. It is intentionally opinionated: it uses the existing codebase as evidence, optimizes for end-user experience, and pushes for simple, robust engineering choices.

## What it does

- Clarifies the real user/product goal.
- Reads the existing codebase when available before making architectural claims.
- Builds and resolves the decision tree behind a proposal step by step.
- Challenges weak assumptions and unnecessary complexity.
- Says no when a design is wrong for the goal, codebase, or end user.
- Ends with a concise Handshake Summary that captures the chosen path, rejected options, non-goals, risks, and open questions.

## Install in pi

Install directly from GitHub:

```bash
pi install git:github.com/mertdeveci5/handshake
```

Or clone locally and load the skill directly:

```bash
git clone https://github.com/mertdeveci5/handshake.git
pi --skill ./handshake/skills/handshake
```

Use it in pi with:

```text
/skill:handshake Stress-test this feature plan...
```

## Use with other Agent Skills-compatible harnesses

The skill lives at:

```text
skills/handshake/SKILL.md
```

Copy or symlink `skills/handshake` into your harness' skill directory, for example:

```bash
mkdir -p ~/.agents/skills
ln -s "$(pwd)/skills/handshake" ~/.agents/skills/handshake
```

For harness-specific directories, copy or symlink the same folder into the directory your tool scans, such as `~/.claude/skills` or `~/.codex/skills` when configured.

## Repository layout

```text
skills/
  handshake/
    SKILL.md
package.json
README.md
LICENSE
```

The `package.json` includes a `pi` manifest so pi can install this repository as a package.

## License

MIT
