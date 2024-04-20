# What is this?

This repo contains a reproduction of a weird behaviour encountered using GitHub CLI in an action.

From the API docs at [https://docs.github.com/en/rest/releases/releases?apiVersion=2022-11-28#list-releases](https://docs.github.com/en/rest/releases/releases?apiVersion=2022-11-28#list-releases), a token with the permission set `contents:read` should suffice.

As this repo showcases, if the token has the permission `contents:read`, the `gh release list --json name` command returns an empty array; if the token has the permission `contents:write`, the `gh release list --json name` command returns the expected releases.

## How to use

### 1. Fork the repo on GH

### 2. Clone the forked repo

Example using HTTPS:

```sh
git clone https://github.com/<your_username>/releases-repro
```

### 3. Make any edits to the test file

### 4. Stage, commit the edits and push the commit

```sh
git add test.txt
git commit -m "testing stuff"
git push
```

### 5. Tag the commit and push the tag

```sh
git tag -a v0.0.1 -m "Test release"
git push origin v0.0.1
```

At this point the workflow should create a draft release automatically.

### 6. Manually run the "List releases" workflow (using the web GUI)

Navigate to `https://github.com/<your_username>/releases-repro/actions/workflows/list-releases.yml`
