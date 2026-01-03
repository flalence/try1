# Tag-Release, tag-triggered auto-release in GitHub

This is a repository demonstrating the tag-release workflow
where you automatically create a GitHub Release
by pushing a git tag representing the semantic version such as `v1.2.3`.
Pushing commits does not trigger the tag-release.
When an auto-release workflow runs, it can create
one or more zip files and make them available in the Release page.

In this repo, the tag-release is configured in this GitHub Actions config file:

- `.github` > `.workflows` > `tag-release.yml`

It creates 2 zip files.
One is a zip file with the contents of the "Release" folder of this repo.
The other is a SHA256 of it.
See the config file for how they are created.
The URL of a zip file is, for example, as follows.

- https://github.com/flalence/tag-release/releases/download/v0.0.4/my-release-v0.0.4.zip

## Set up

Make sure that the local repository is using the intended user.

```bash
git config user.name
git config user.email
```

## Creating and pushing a git tag

See the existing tags in a local git repository.

```bash
git tag
```

Create a new tag.

```bash
git tag v1.0.0
```

Check that the intended tag is pointing at HEAD.

```bash
git tag --points-at HEAD
```

Push the tag to the remote repository in GitHub.

```bash
git push origin v1.0.0
```

If a GitHub Actions YML file is configured to react to a git tag being pushed,
the above push starts a CI process for it.

## Trouble shooting authentication issues on Windows

If the push fails due to authentication issues on Windows,
check the cache for Windows Credential Manager.

1. Open the Control Panel.
2. Search "Credential Manager".
3. Select "Windows Credentials".
4. Delete entries related to GitHub.

Then try pushing again.

## See also

GitHub Actions > Check out

- https://github.com/actions/checkout

GitHub Action for creating GitHub Releases

- https://github.com/softprops/action-gh-release

_Copyright 2025-2026 Flalence_
