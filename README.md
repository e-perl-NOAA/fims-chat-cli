# fims-chat-cli

A specialized CLI environment for exploring, using, and maintaining the NOAA FIMS ecosystem with Copilot (this could be expanded for Gemini, Codex, and Claude but NMFS only has (LIMITED) access to Copilot at this moment).

## Overview

This repository provides a ready-to-use setup for agent CLI that can answer questions about:
- The FIMS ecosystem (core packages, diagnostics, RTMB, and case studies)
- Package implementation details, usage, and code structure
- Working with FIMS and workflows (examples, debugging, and integration guidance)
- Developing and maintaining FIMS packages (bug fixes, tests, docs, and release support)
- Cross-package comparisons and recommendations
- Community-facing documentation and metadata

The key insight: modern coding agents are excellent at navigating repositories to answer questions. This repo houses the FIMS package repos as git submodules, allowing agents to search through them and answer your questions with citations.

## Quick Start

### Prerequisites
- Copilot access on GitHub or via CLI
    - If using the Copilot CLI:
    - [Copilot](https://github.com/features/copilot/cli) installed and authenticated:
    - Git 2.13+ (for submodule support)

### Clone the Repository

**Important:** You must clone with the `--recursive` flag to download all FIMS packages:

```bash
git clone --recursive https://github.com/e-perl-NOAA/fims-chat-cli.git
cd fims-chat-cli
```

**Or**, if you already cloned without `--recursive`:

```bash
git clone https://github.com/e-perl-NOAA/fims-chat-cli.git
cd fims-chat-cli
git submodule update --init --recursive
```

### Start Chatting

Run the agent you want to use:

```bash
copilot
```

## Ask Questions Like:

### Basic FIMS Questions
- "What is some basic information about FIMS?"
- "Where are the case studies located?"
- "What is the recommended FIMS workflow from configuration to diagnostics?"
- "Where is the FIMS roadmap or community info?"

### Package-Specific Questions
- "How do I run a basic FIMS model?"
- "Show me how FIMS handles fleets and populations."
- "How does FIMSRTMB differ from core FIMS?"

### Cross-Cutting Questions
- "Which repo has diagnostics and residual plots?"
- "Where are the example configurations used in case studies?"

### Learning and Workflow Topics
- "Walk me through a minimal config -> fit -> diagnostics workflow."
- "Which case study is closest to a small pelagic example?"

### Development Help
- "Help me add tests for this bug in FIMS and update the docs."
- "Where are the gtest templates and how do I use them?"
- "Which tests cover configuration parsing?"

## For FIMS Users and Developers

You can use this repo as a practical maintenance and development workspace across the FIMS ecosystem. Tasks might include:
- Getting help aligning code with FIMS patterns and best practices
- Tracing where behavior is implemented across packages
- Prototyping fixes and adding tests
- Updating docs and examples to match code changes

## Repository Structure

```
fims-chat-cli/
├── fims-packages/
│   ├── fims/                    # Core FIMS package (main) and docs
│   ├── fims-dev/                # Core FIMS package (dev) and docs
│   ├── noaa-fims.github.io/     # Website and community docs
│   ├── case-studies/            # Examples and workflows
│   ├── FIMSdiags/               # Diagnostics tools
│   └── FIMSRTMB/                # RTMB tooling
└── .github/
		├── copilot-instructions.md  # Copilot guidance for FIMS-Chat
```

## Keeping Packages Updated

This repository automatically updates all FIMS package submodules via GitHub Actions.

To update locally from the repository as it does this automatically run the following in a terminal opened up where the repo lives:

```bash
git pull
```

## How It Works

1. **Git Submodules**: Each FIMS package is a git submodule pointing to its official repository
2. **Full Git History**: Each agent can access the complete development history of each package
4. **Agent Instructions**: Copilot instructions guide the chat CLI to search packages, cite sources, and acknowledge limits

## Contributing

This is an experiment in AI-assisted FIMS support. Contributions welcome:
- Add missing FIMS packages
- Improve Copilot instructions in [/.github/copilot-instructions.md](.github/copilot-instructions.md)
- Share interesting use cases

## Notes

- First clone may take several minutes and several GB of disk space
- Your selected agent may require an active subscription and/or API access
- This is a community tool, not an official NOAA release
- For authoritative answers, consult official package documentation

## License

This repository structure is provided as-is. Individual packages retain their original licenses.