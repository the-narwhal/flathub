# Proton Authenticator

Flatpak for [Proton Authenticator](https://proton.me/authenticator), a 2FA code app from Proton.

This is a community package. Please report app bugs to Proton directly and flatpak packaging bugs here.

## How it's built

Built from source from [ProtonMail/WebClients](https://github.com/ProtonMail/WebClients) (`applications/authenticator`).

## Permissions

- `--talk-name=org.freedesktop.secrets` stores the app's database key in the keyring. Without it the app asks if you want to keep the key in local storage instead.
- Network is used for sign-in and sync.

## Updating

1. Change the WebClients commit in `me.proton.Authenticator.yml`.
2. Regenerate the sources:

   ```
   tools/update-sources.sh <commit>
   ```

3. Build and test locally before opening a PR:

   ```
   flatpak run org.flatpak.Builder --user --install --force-clean build me.proton.Authenticator.yml
   ```
