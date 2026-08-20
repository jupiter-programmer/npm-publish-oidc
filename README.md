# `npm-package` Publish with OIDC

A GitHub Actions workflow for securely publishing npm packages using **OIDC Trusted Publishing**.

## Publish a New Version

### 1. Commit Your Changes

```bash
git add .
git commit -m "feat: add new feature"
git push
```

### 2. Update the Package Version

```bash
npm version patch
```
- This automatically updates the package version.
- You can also use `minor` or `major` instead of `patch`.

### 3. Create and Push the Git Tag

Create a tag matching your new package version:

```bash
git tag v1.0.2
```

If the tag already exists locally, delete it first:

```bash
git tag -d v1.0.2
```

Then create the tag again:

```bash
git tag v1.0.2
```

Push the version tag:

```bash
git push origin v1.0.2
```

> Replace `v1.0.2` with your actual package version.

Once the tag is pushed, GitHub Actions will automatically publish the package to npm.

### 4. Push Version Changes

If the version changes have not already been pushed:

```bash
git add .
git commit -m "chore: update package version"
git push
```

### Build

- No need to build the package manually. 
- The GitHub Actions workflow automatically handles the build, tests, and npm publishing process.
