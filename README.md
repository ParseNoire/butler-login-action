# `butler` login action

Sets the `BUTLER_API_KEY` environment variable for use by `butler`.

## Usage

```yaml
name: my-workflow

on: push

jobs:
  login:
    runs-on: ubuntu-latest
    container: ghcr.io/parsenoire/butler:latest
    steps:
      - uses: parsenoire/butler-login-action@v1
        with:
          credentials: ${{ secrets.BUTLER_API_KEY }}
```

The image [ghcr.io/parsenoire/butler](https://ghcr.io/parsenoire/butler) from GitHub Container Registry is used in this example, but this action should work in other environments where `butler` reads the credentials from `BUTLER_API_KEY`.
