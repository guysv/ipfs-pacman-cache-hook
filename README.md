## ipfs-pacman-cache-hook
> A pacman hook to add newly-installed packages to [IPFS](https://github.com/ipfs/go-ipfs)

### Usage TLDR

```bash
# Installation
makepkg -i
systemctl --user enable --now ipfs-pacman-cache.path 

# Logs
journalctl --user -u ipfs-pacman-cache.service
```

### Why

In the case you are using [arch-mirror](https://github.com/victorb/arch-mirror)
and got timed out, you're probably going to fallback to one of the traditional mirrors.
But then, the next peer to download that package is going to face the same situation.
If you got your package, seed it for the others!
