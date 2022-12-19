# net.splitcells.network.community.git-bug

This repo is a ticket system via [git-bug](https://github.com/MichaelMure/git-bug).

# Commands

Pure git versions are documented for portability purposes,
where git repo synchronization is concerned.
Requiring to install and use git-bug for ticket synchronization on git level,
creates an unreasonable software stack requirement.

## Pull git-bug data via pure git.
* `git fetch origin 'refs/identities/*:refs/identities/*'`
* `git fetch origin 'refs/bugs/*:refs/bugs/*'`
## Push git-bug data via pure git.
* `git push origin 'refs/bugs/*:refs/identities/*'`
* `git push origin`
## Import issue data from GitHub.
Register GitHub repo for future issue imports.

```bash
git bug bridge configure \
    --name=GitHub \
    --target=github \
    --url=--url=https://github.com/www-splitcells-net/net.splitcells.network  \
    --login=<login-name> \
    --token=<token>
```

Import issue data from GitHub.

```git bug bridge pull GitHub```