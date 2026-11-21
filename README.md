# Codex CLI 0.169.0 for Android ARMv7 (32-bit)

An unofficial community build of OpenAI Codex CLI for 32-bit ARMv7 Termux on Android 12 (API 31) or later. This build is not produced or supported by OpenAI.

## Download and install

In your terminal, download the archive from the [v0.169.0 ARMv7 release](https://github.com/Danny-60743/codex-32-bit/releases/tag/v0.169.0-android-armv7), then run:

```sh
curl -L -o codex-0.169.0-android-armv7.tar.gz \
  https://github.com/Danny-60743/codex-32-bit/releases/download/v0.169.0-android-armv7/codex-0.169.0-android-armv7.tar.gz

sha256sum codex-0.169.0-android-armv7.tar.gz
```

Check that the SHA-256 output is:

```text
1a9a44e679d6829d5da0da4ef02d6e653819466fd0f0f59a45baa02db45b1403
```

Then extract and install:

```sh
tar -xzf codex-0.169.0-android-armv7.tar.gz
cd codex-0.169.0-android-armv7
sh install.sh
hash -r
codex --version
codex --no-daemon
```

The installer creates a versioned installation directory and updates the `codex` command symlink. It leaves existing Codex settings and account data in place and keeps older versioned releases.

## Android ARM32 limitations

This experimental port does not support the daemon, V8 memory-hardening sandbox, or Android OS command sandbox. Commands can use the permissions granted to Termux. The default permission profile may fail when a turn starts because this build cannot enforce its filesystem sandbox.

For a project you trust, the bundled README suggests running with on-request approvals and full access:

```sh
codex --no-daemon --sandbox danger-full-access --ask-for-approval on-request
```

Full access allows Codex to use Termux's file and command permissions. Use this only with projects and JavaScript you trust.

The archive includes `VALIDATION.txt`, `LICENSE`, `NOTICE`, third-party licenses, build details, and source patches. The build is based on [OpenAI Codex source tag `rust-v0.169.0`](https://github.com/openai/codex/tree/rust-v0.169.0).
