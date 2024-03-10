# cctl
A simple (bash) command proxy with OpenSSH support, to provide similar functionality that of kubectl's contexts, but for regular containers.

This was just thrown together in 20 minutes, it took more time to write this file, BUT I would like to keep evolving this gradually.


**State:** PRE-ALPHA 

## How it works
Uses the local file .cctl as persistence, this is where context is stored, that is the current target node for container commands.
The target nodes can be fuzzy selected, the selection uses the .ssh/config file to grep the available & pre-configured hosts.

## Setup
For inital phase, testing & simplicity, I have just added the project directory to PATH, but the following also works

```bash
    git clone https://github.com/nandor-magyar/cctl
    cd cctl
    sudo cp {cctl,cctx} /usr/local/bin/
```

## Roadmap

- auto-completion (SSH incl.)
- dynamic/multiple container runtimes (docker, podman... yours?)

If this "command-proxy" proves to be useful, a generic tool could be made to serve the same purpose using Go instead of bash.

## Suggested Aliases
```
alias c="cctl "
alias cx="cctx "
```

## Dependencies
- bash
- sed
- fzf (for fuzzy context selection)
- a container runtime
- OpenSSH (.ssh/config file with entries)


Feel free to leave feeback in any form!
