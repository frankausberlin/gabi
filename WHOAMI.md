# WHOAMI.md - Gabi's Understanding of Host System

👻 *Living document – ​​continuously updated as new information about the environment becomes available.*

## Host System Overview

### 🖥️ Hardware
- **Hostname**: ubi
- **Device**: Gigabyte K5 Laptop
- **GPU**: NVIDIA RTX 4060 Ti (8GB VRAM)
- **RAM**: 40 GB
- **IP**: 192.168.178.38
- **Network**: Home network with 9 devices (tablets, phones, SBCs, TVs)
- **Internet**: 500 Mb/s

### 🐧 Operating System
- **OS**: Linux 6.17.0-8-generic (x64)
- **Distribution**: Likely Ubuntu-based (given `gh` package version)
- **User**: frank
- **Timezone**: Europe/Berlin (GMT+1)

### 🐍 Python Ecosystem (CRITICAL)

#### Core Philosophy
- **`rlb` alias**: Reloads bash, activates appropriate Python environment
- **Auto-activation logic**: Checks for `.venv` in current directory, activates if found; otherwise activates `ds12` mamba environment
- **Project isolation**: Each project should have its own `uv` venv

#### Key Environments
1. **`ds12`** (Data Science environment)
   - Mamba-based environment for quick experiments
   - Contains "all the goodies": PyTorch, TensorFlow, JAX, Jupyter, ML libs
   - Recreated with comprehensive install script
   - Activated by default when no project `.venv` exists

2. **Project-specific uv venvs**
   - Created with `uv` (fast Python package installer)
   - Located as `.venv` in project root
   - Takes precedence over `ds12` when present

#### Important Commands
```bash
rlb                    # Reload bash, auto-activate environment
act ds12               # Activate data science environment ds12 and remember ds12 in .lastenv
uv venv                # Create new project venv
pyinit                 # Project initialization (from ~/.bash_lib)
cw                     # Without a dot, the directory to be changed is: ~/.config/current working folder
                       # with a dot, the current directory is written to the current_working_folder file.
```

#### Environment Detection Flow
```
Current Directory → Check for .venv/ → YES → Activate .venv
                               ↓ NO
                         Activate ds12
```

### 🔧 Development Tools

#### Git & GitHub
- **GitHub CLI**: `gh` installed and authenticated as `frankausberlin`
- **Token scopes**: 'gist', 'read:org', 'repo', 'workflow'
- **Default branch**: Changed from 'master' to 'main'

#### Package Managers
- **Mamba**: Primary environment manager (Conda replacement)
- **UV**: Fast Python package installer for project venvs
- **NPM**: Node package manager (for OpenClaw skills)

#### Shell Customizations
- **`~/.bash_aliases`**: Aliases collection for everything
- **`~/.bash_lib`**: Custom functions like `pyinit`
- **`~/.startenv`**: tracks last activated environment
- **`~/.config/_exports/`**: folder auf auto-exports
- **`~/.lasterror`**: auto-generated last bash error log for agent-use

### 📁 Directory Structure

#### Primary Workspaces
- **`~/labor`**: Main working directory
- **`~/labor/gits/`** : GitHub repositories 

### 🛠️ Available Services

#### MCP Servers (from KiloCode)
- ~/.config/Code/User/globalStorage/kilocode.kilo-code/settings/mcp_settings.json
- **context7**: Upstash Context7 documentation search
- **sequentialthinking**: Sequential Thinking server
- **github**: Github access to user frankausberlin
- **playwright**: Playwright browser automation
- **searxng**: SearXNG search engine (localhost:8088)
- **desktop-commander**: Desktop Commander (currently offline)
- **stackoverflow**: Stack Overflow search

#### Network Devices (SSH Access)
- **ubu**: `ssh frank@ubu` (Ubuntu Server)
- **doogee**: `ssh -p 8022 u0_a202@doogee` (Doogee Tablet, Termux)
- **redmi**: `ssh -p 8022 u0_a470@redmi` (Redmi Smartphone, Termux)
- **teci**: `ssh -p 8022 u0_a218@teci` (Teclast Tablet, Termux)

### 🧠 AI & Development Context

#### Frank's Profile
- **GitHub**: frankausberlin (24 repositories)
- **Interests**: MCP/Agent development, AI/ML tools, CLI tools, workflow automation
- **Notable Projects**: adminmcp, tuible, lazy_student, Ragflow
- **Community**: C-Base Berlin computer club, Robert Crumb fan ("Fritz the Cat")

---
