# Try auto-release

Try GitHub Actions to automatically create releases
when you push tags to your repository.

## Set up

```bash
git config user.name
git config user.email
```

## Tag

See the existing tags in a local repository.

```bash
git tag
```

Create a new tag.

```bash
git tag v1.0.0
```

Check that the intended tag is pointing to the HEAD.

```bash
git tag --points-at HEAD
```

Push the tag to the remote repository in GitHub.

```bash
git push origin v1.0.0
```

## In case of authentication issues for using push

Windows Credential Manager may interfere.

Open the Control Panel, search "Credential Manager", and select "Windows Credentials".
Delete any entries related to GitHub.

Then try pushing again.
