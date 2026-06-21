# Contributing to stressthis

stressthis is a **pointer catalog** - lists of tools, with links to their upstream repos. There
is no code, no build step, and nothing to install. Contributing means editing markdown and one
JSON file.

## Inclusion bar

List a tool if it is:

1. **Open source / freely installable** under an identifiable license (any license is fine -
   we only link to it, we don't redistribute it).
2. **Maintained** - meaningful recent activity, or a stable, still-working tool.
3. **Real** - link the genuine upstream project; no typosquats or hijacked forks.
4. **Relevant** - it actually finds bugs or stresses a system in one of the 16 categories.

## How to add or correct a tool

Edit three places so they stay consistent:

1. **`tools/<category>.md`** - add a row to the table:
   `| [Tool name](upstream-url) | what it does | when to use it | install hint | ` `` `SPDX` `` ` |`
   Append a ` ⚠️` after the license if it is copyleft (GPL/AGPL) or commercial.
2. **`catalog/index.json`** - add an entry under `"tools"` with the same fields the other entries
   use (`name`, `category`, `summary`, `when_to_use`, `upstream`, `install`, `usage`, `license`,
   `copyleft`, `languages`, `bug_classes`, `popularity`), and bump `tool_count` and the
   category's `count`. This is the file agents actually read, so keep it accurate.
3. **`THIRD-PARTY-LICENSES.md`** - add the tool to its category table (name, upstream, SPDX,
   copyleft yes/no).

## Get the license right

The `license` / `copyleft` fields matter: an agent uses them to decide what it may install vs.
what it must never copy into a user's project. Verify the SPDX identifier against the upstream
repo's actual LICENSE file. When in doubt, mark `copyleft: true` (install-from-upstream only).

## Quality of the entry

Write the `summary` and `when_to_use` for the agent that will read them: what bug class does it
find, and when should it (or should it NOT) be chosen. A good "don't use this when..." signal is
as useful as the "use this when...".

By contributing you agree your additions to this repo's own content are licensed under its
[MIT license](LICENSE). (The listed tools remain under their own licenses.)
