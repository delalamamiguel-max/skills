> **Note:** This repository contains Anthropic's implementation of skills for Claude. For information about the Agent Skills standard, see [agentskills.io](http://agentskills.io).

# Skills
Skills are folders of instructions, scripts, and resources that Claude loads dynamically to improve performance on specialized tasks. Skills teach Claude how to complete specific tasks in a repeatable way, whether that's creating documents with your company's brand guidelines, analyzing data using your organization's specific workflows, or automating personal tasks.

For more information, check out:
- [What are skills?](https://support.claude.com/en/articles/12512176-what-are-skills)
- [Using skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [How to create custom skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [Equipping agents for the real world with Agent Skills](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

# About This Repository

This repository contains skills that demonstrate what's possible with Claude's skills system. These skills range from creative applications (art, music, design) to technical tasks (testing web apps, MCP server generation) to enterprise workflows (communications, branding, etc.).

Each skill is self-contained in its own folder with a `SKILL.md` file containing the instructions and metadata that Claude uses. Browse through these skills to get inspiration for your own skills or to understand different patterns and approaches.

Many skills in this repo are open source (Apache 2.0). We've also included the document creation & editing skills that power [Claude's document capabilities](https://www.anthropic.com/news/create-files) under the hood in the [`skills/docx`](./skills/docx), [`skills/pdf`](./skills/pdf), [`skills/pptx`](./skills/pptx), and [`skills/xlsx`](./skills/xlsx) subfolders. These are source-available, not open source, but we wanted to share these with developers as a reference for more complex skills that are actively used in a production AI application.

## Disclaimer

**These skills are provided for demonstration and educational purposes only.** While some of these capabilities may be available in Claude, the implementations and behaviors you receive from Claude may differ from what is shown in these skills. These skills are meant to illustrate patterns and possibilities. Always test skills thoroughly in your own environment before relying on them for critical tasks.

# Skill Sets
- [./skills](./skills): Skill examples for Creative & Design, Development & Technical, Enterprise & Communication, and Document Skills
- [./spec](./spec): The Agent Skills specification
- [./template](./template): Skill template

# Try in Claude Code, Claude.ai, and the API

## Claude Code
You can register this repository as a Claude Code Plugin marketplace by running the following command in Claude Code:
```
/plugin marketplace add anthropics/skills
```

Then, to install a specific set of skills:
1. Select `Browse and install plugins`
2. Select `anthropic-agent-skills`
3. Select `document-skills` or `example-skills`
4. Select `Install now`

Alternatively, directly install either Plugin via:
```
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```

After installing the plugin, you can use the skill by just mentioning it. For instance, if you install the `document-skills` plugin from the marketplace, you can ask Claude Code to do something like: "Use the PDF skill to extract the form fields from `path/to/some-file.pdf`"

## Claude.ai

These example skills are all already available to paid plans in Claude.ai. 

To use any skill from this repository or upload custom skills, follow the instructions in [Using skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude#h_a4222fa77b).

## Claude API

You can use Anthropic's pre-built skills, and upload custom skills, via the Claude API. See the [Skills API Quickstart](https://docs.claude.com/en/api/skills-guide#creating-a-skill) for more.

# Creating a Basic Skill

Skills are simple to create - just a folder with a `SKILL.md` file containing YAML frontmatter and instructions. You can use the **template-skill** in this repository as a starting point:

```markdown
---
name: my-skill-name
description: A clear description of what this skill does and when to use it
---

# My Skill Name

[Add your instructions here that Claude will follow when this skill is active]

## Examples
- Example usage 1
- Example usage 2

## Guidelines
- Guideline 1
- Guideline 2
```

The frontmatter requires only two fields:
- `name` - A unique identifier for your skill (lowercase, hyphens for spaces)
- `description` - A complete description of what the skill does and when to use it

The markdown content below contains the instructions, examples, and guidelines that Claude will follow. For more details, see [How to create custom skills](https://support.claude.com/en/articles/12512198-creating-custom-skills).

# Partner Skills

Skills are a great way to teach Claude how to get better at using specific pieces of software. As we see awesome example skills from partners, we may highlight some of them here:

- **Notion** - [Notion Skills for Claude](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0)


---

# Owned checkout guide

## Purpose and status

This owned reference checkout preserves the Anthropic Skills README above. It contains example agent skills and document-processing skills, not a deployed application or evidence that these skills are installed in an owner workspace. Upstream examples and availability claims have not been independently runtime-validated here.

## Repository map

[`skills/`](skills/) contains individual skill instructions, references and optional scripts/assets; [`template/`](template/) supplies a starting template; [`spec/`](spec/) contains specification references. [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json) groups document skills, example skills and the Claude API skill. [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md) preserves third-party notices.

## Architecture and integrations

A compatible agent discovers skill metadata and loads instructions and supporting resources when applicable. Bundled scripts and integrations vary by skill; this is not one shared service with a single runtime. Marketplace registration and skill execution are separate operations from cloning this repository.

## Setup and environments

Follow the upstream host-specific setup only for a separately authorized installation. There is no universal root dependency installation or environment file for every skill. Inspect the chosen skill’s instructions, scripts, dependencies and permissions first. Do not copy provider credentials or private input documents into this public reference checkout.

## Safe commands

For documentation review, use local, read-only Git inspection: `git status --short`, `git ls-files`, `git diff -- README.md`, and `git diff --check`. Inspect scripts as text before considering execution. Installation, build, test, authentication and publication commands shown in the upstream documentation are outside this README-only review.

## Testing and validation

For this guide, validation is limited to Markdown structure, newly added relative paths, diff whitespace and preservation of the original README. Skill scripts and host integrations were not run. Validation requirements are specific to the selected skill and host; no repository-wide application test result is implied.

## Deployment and rollback

There is no owner deployment established by this checkout. Installing a marketplace/plugin changes the receiving agent environment and needs separate review. A README rollback is a local documentation revert; it does not uninstall skills or reverse any actions performed by a host. Installed versions and rollback procedures remain unverified.

## Risks and guardrails

Licensing is not uniform across this repository. Preserve each skill’s applicable terms and the third-party notices. The document skills are described upstream as source-available, not open source; do not treat an Apache license in an example folder as permission covering every folder. Review skill instructions as executable agent guidance before enabling them. No skills were invoked during this documentation work.

## Related documentation

Start with the upstream usage and disclaimer above, the [template](template/), [specification references](spec/), [marketplace manifest](.claude-plugin/marketplace.json) and [third-party notices](THIRD_PARTY_NOTICES.md). Consult the applicable license inside the selected skill folder.
