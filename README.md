# FADs website

## Deployment

This project uses `pnpm`. It has not been tested with other package managers.

To deploy simply run:

```bash
pnpm run deploy
```

### Issues

If you get an error like this:

```bash
ProcessError: fatal: a branch named 'gh-pages' already exists
```

There's likely that the build process was interrupted. Running the following should clean the `.git` cache:

```bash
git fetch --prune
```
