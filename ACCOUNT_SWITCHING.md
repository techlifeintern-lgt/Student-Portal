# Switching GitHub Accounts for This Repository

These steps use Git Credential Manager (GCM) with an HTTPS Git remote. They do not require the GitHub CLI (`gh`).

## Check saved GitHub accounts

```powershell
git credential-manager github list
```

## Add an account

If the account you want is not listed, run this and complete the sign-in flow:

```powershell
git credential-manager github login
```

Check the account list again:

```powershell
git credential-manager github list
```

## Select an account for this repository

Set the account name you want Git to use for GitHub HTTPS authentication. This setting is local to this repository:

```powershell
git config --local credential.https://github.com.username techlifeintern-lgt
```

Confirm the setting:

```powershell
git config --local --get credential.https://github.com.username
```

To use another account later, replace `techlifeintern-lgt` with that account's GitHub username and run the config command again.

## Push a branch

For the first push of a branch, set its upstream. For `main`:

```powershell
git push --set-upstream origin main
```

For another branch, replace `main` with the branch name:

```powershell
git push --set-upstream origin <branch-name>
```

After the upstream is set, future pushes from that branch can usually use:

```powershell
git push
```

The selected GitHub account still needs write access to the repository.
