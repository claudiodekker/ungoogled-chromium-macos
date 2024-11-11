# Signed "ungoogled-chromium" for macOS builds

This repository hosts [code-signed and notarized builds](https://support.apple.com/guide/security/app-code-signing-process-sec3ad8e6e53/web) of [ungoogled-software/ungoogled-chromium-macos](https://github.com/ungoogled-software/ungoogled-chromium-macos).

> [!WARNING]
> As of [Ungoogled-Chromium macOS 130.0.6723.116-1.1](https://github.com/ungoogled-software/ungoogled-chromium-macos/releases/tag/130.0.6723.116-1.1), the official Ungoogled Chromium repository is now signing builds using Apple Developer ID certificate `Developer ID Application: Qian Qian (B9A88FL5XJ)`. Because of this, this repository is now deprecated and archived. You can find the latest code-signed builds here: https://github.com/ungoogled-software/ungoogled-chromium-macos/releases

## What's the benefit of these notarized builds?

Your version of macOS will be able to verify that `Chromium.app` hasn't been tampered with, that to Apple's knowledge the application is safe to run, and that the signer of the application (in this case, me / this repository) has stated as such.

Additionally, it provides applications with the means to trust your Chromium installation. For example, Little Snitch will be able to monitor and perform [process identity checks](https://help.obdev.at/littlesnitch5/adv-code-identity-checks), and 1Password will be able to [trust your browser](https://1password.community/discussion/140735/extending-support-for-trusted-web-browsers) and auto-unlock the extension for you.

## Frequently asked questions (FAQs)

### Q: Even with this version of Chromium added to 1Password's trusted browsers, the extension won't auto unlock. Why?

That's [a somewhat long story](https://github.com/claudiodekker/ungoogled-chromium-macos/issues/1), but the fix is pretty straight forward.
All you'll have to do is create a 1Password NativeMessagingHost manifest file for Chromium. The easiest way to do so is to simply copy Chrome's:

```bash
mkdir -p ~/Library/Application\ Support/Chromium/NativeMessagingHosts/
cp ~/Library/Application\ Support/Google/Chrome/NativeMessagingHosts/com.1password.1password.json ~/Library/Application\ Support/Chromium/NativeMessagingHosts/com.1password.1password.json
```

### Q: I have a different question that isn't listed.

If your question wasn't listed here, please check the README over at the [ungoogled-software/ungoogled-chromium-macos](https://github.com/ungoogled-software/ungoogled-chromium-macos) repository, the [ungoogled-software/ungoogled-chromium](https://github.com/ungoogled-software/ungoogled-chromium) repository, or the FAQ's on their Wiki: [https://ungoogled-software.github.io/ungoogled-chromium-wiki/faq](https://ungoogled-software.github.io/ungoogled-chromium-wiki/faq)
