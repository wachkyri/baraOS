<p align="center">
  <img src="/repo_content/Bazzite_Tagline.svg?raw=true" alt="Bazzite"/>
</p>

[![build-bazzite](https://github.com/ublue-os/bazzite/actions/workflows/build.yml/badge.svg)](https://github.com/ublue-os/bazzite/actions/workflows/build.yml)

---
# Table of Contents
- [Features for **All** Bazzite Images](https://github.com/ublue-os/bazzite#about--features)
  - [Features for **Desktop** Images](https://github.com/ublue-os/bazzite#desktop)
  - [Features for **GNOME** Images](https://github.com/ublue-os/bazzite#gnome)
  - [Features from Upstream](https://github.com/ublue-os/bazzite#features-from-upstream)
- [Why & Frequently Asked Questions](https://github.com/ublue-os/bazzite#why)
- [Showcase & Newsletter](https://github.com/ublue-os/bazzite#showcase)
- [Custom Packages](https://github.com/ublue-os/bazzite#custom-packages)
- [Verification & Metrics](https://github.com/ublue-os/bazzite#verification)
- [Special Thanks](https://github.com/ublue-os/bazzite#special-thanks)
- [Building Your Own](https://github.com/ublue-os/bazzite#build-your-own)
- [Community](https://github.com/ublue-os/bazzite#join-the-community)
---

## About & Features

BaraOS is an OCI image built from [ublue-os/main](https://github.com/ublue-os/main) and forked from the [Bazzite](https://github.com/ublue-os/bazzite) project. It is an experimental project to tailor an OS for my own purpose. I don't recommend using it.

### Desktop

Common variant available as `bazzite`, suitable for desktop computers.

- Automatic updates for the OS, Flatpaks, Nix packages <sup><sub>(Via Fleek)</sub></sup>, and all Distrobox containers.

> [!IMPORTANT]  
> **ISOs can be downloaded from the releases page [here](https://github.com/ublue-os/bazzite/releases), and a helpful install guide can be found [here](https://universal-blue.discourse.group/docs?topic=30).** If you experience any issues with installing Bazzite, then check out the [troubleshoot guide](https://universal-blue.discourse.group/docs?topic=34).

If you're on an existing Universal Blue image follow [these instructions](https://universal-blue.org/images/#image-list). To rebase an existing upstream Fedora Silverblue/Kinoite ostree system to this image:

```bash
rpm-ostree rebase ostree-unverified-registry:ghcr.io/ublue-os/bazzite:latest
```

**For users with Secure Boot enabled:** Run `ujust enroll-secure-boot-key` and enter the password `ublue-os` if prompted to enroll the required key.

### GNOME

Builds with the GNOME desktop environment are available in both desktop and deck flavors. These builds come with the following additional features:

- [Variable refresh rate support and fractional scaling enabled under Wayland](https://gitlab.gnome.org/GNOME/mutter/-/merge_requests/1154).
- Custom menu in the top bar for returning to game mode, launching Steam, and opening a number of useful utilities. <sub><sup>(Only on Steam Deck builds)</sup></sub>
- [GSConnect](https://extensions.gnome.org/extension/1319/gsconnect/) preinstalled and ready to use.
- Features optional Valve-inspired themes matching Vapor and VGUI2 from SteamOS.
- [Hanabi extension](https://github.com/jeffshee/gnome-ext-hanabi) included to offer similar features to Wallpaper Engine in KDE.
- Numerous optional extensions pre-installed, including [important user experience fixes](https://www.youtube.com/watch?v=nbCg9_YgKgM).
- Automatic updates for the [Firefox GNOME theme](https://github.com/rafaelmardojai/firefox-gnome-theme) and [Thunderbird GNOME theme](https://github.com/rafaelmardojai/thunderbird-gnome-theme). <sup><sub>(If installed)</sub></sup>

> [!IMPORTANT]  
> **ISOs can be downloaded from our releases page [here](https://github.com/ublue-os/bazzite/releases), and a helpful install guide can be found [here](https://universal-blue.discourse.group/docs?topic=30).** If you experience any issues with installing Bazzite, then check out our [troubleshoot guide](https://universal-blue.discourse.group/docs?topic=34).

To rebase an existing ostree system to the **desktop** release:

```bash
rpm-ostree rebase ostree-unverified-registry:ghcr.io/ublue-os/bazzite-gnome:latest
```

### Features from Upstream

#### Universal Blue

- Flathub is enabled by default.
- [`just`](https://github.com/casey/just) commands for convenience.
- Multi-media codecs out of the box.
- Rollback Bazzite from any build within the last 90 days.

#### Features from Fedora Linux (Kinoite & Silverblue)

- A rock solid and stable base.
- System packages stay relatively up to date.
- Can layer Fedora packages to the image without losing them between updates.
- Security focused with [SELinux](https://github.com/SELinuxProject/selinux) preinstalled and configured out of the box.
- The ability to rebase to different Fedora libostree images, if desired, without losing user data.
- Printing support thanks to [CUPS](https://www.cups.org/) being preinstalled.

## Why

Bazzite started as a project to resolve some of the issues that plague SteamOS, mainly out of date packages (despite an Arch base) and the lack of a functional package manager.

Despite this project also being image-based, you are able to install any Fedora package straight from the command line. These packages will persist across updates <sub><sup>(So go ahead and install that obscure VPN software you spent an hour trying to get working in SteamOS)</sup></sub>. Additionally, Bazzite is updated multiple times a week with packages from upstream Fedora, giving you the best possible performance and latest features - all on a stable base.

Bazzite ships with the latest Linux kernel and SELinux enabled by default with full support for secure boot <sub><sup>(Run `ujust enroll-secure-boot-key` and enter the password `ublue-os` if prompted to enroll our key)</sup></sub> and disk encryption, making this a sensible solution for general computing. <sup><sub>(Yes, you can print from Bazzite)</sub></sup>

Check out the [Frequently Asked Questions](https://universal-blue.discourse.group/docs?topic=33) for details on what makes Bazzite stand out from other Linux operating systems.

## Showcase

![KDE Vapor Theme](/repo_content/desktop1.png?raw=true "KDE Vapor Theme")
![KDE VGUI2 Theme](/repo_content/desktop2.png?raw=true "KDE VGUI2 Theme")
![Steam Game Mode](/repo_content/gamemode.png?raw=true "Steam Game Mode")
![Waydroid](/repo_content/waydroid.png?raw=true "Waydroid")
![Distrobox Terminals](/repo_content/distrobox.png?raw=true "Distrobox Terminals")
![GNOME Vapor Theme](/repo_content/gnome1.png?raw=true "GNOME Vapor Theme")
![GNOME VGUI2 Theme](/repo_content/gnome2.png?raw=true "GNOME VGUI2 Theme")

Check out our [newsletters](https://universal-blue.discourse.group/tag/bazzite-buzz) and [announcements](https://universal-blue.discourse.group/tags/c/bazzite/5/announcements) that get published on a regular basis for updates on the project.

## Custom Packages

Ported SteamOS and ChimeraOS packages, among others used by Bazzite, are built on Copr in [bazzite](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/) and [bazzite-multilib](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite-multilib/).

|Package|Status|
|---|---|
|[discover-overlay](https://github.com/trigg/Discover)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/discover-overlay/status_image/last_build.png?)|
|ds-inhibit|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/ds-inhibit/status_image/last_build.png?)|
|duperemove|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/duperemove/status_image/last_build.png?)|
|[extest](https://github.com/Supreeeme/extest)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite-multilib/package/extest/status_image/last_build.png?)|
|gamescope|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite-multilib/package/gamescope/status_image/last_build.png?)|
|[gamescope-session-plus](https://github.com/ChimeraOS/gamescope-session)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/gamescope-session-plus/status_image/last_build.png?)|
|[gamescope-session-steam](https://github.com/ChimeraOS/gamescope-session-steam)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/gamescope-session-steam/status_image/last_build.png?)|
|galileo-mura|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/galileo-mura/status_image/last_build.png?)|
|[gnome-randr-rust](https://github.com/maxwellainatchi/gnome-randr-rust)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/gnome-randr-rust/status_image/last_build.png?)|
|gnome-shell-extension-bazzite-menu|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/gnome-shell-extension-bazzite-menu/status_image/last_build.png?)|
|[gnome-shell-extension-caribou-blocker](https://extensions.gnome.org/extension/1326/block-caribou/)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/gnome-shell-extension-caribou-blocker/status_image/last_build.png?)|
|[gnome-shell-extension-hanabi](https://github.com/jeffshee/gnome-ext-hanabi)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/gnome-shell-extension-hanabi/status_image/last_build.png?)|
|[gnome-shell-extension-compiz-windows-effect](https://github.com/hermes83/compiz-windows-effect)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/gnome-shell-extension-compiz-windows-effect/status_image/last_build.png?)|
|jupiter-fan-control|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/jupiter-fan-control/status_image/last_build.png?)|
|jupiter-hw-support-[btrfs](https://gitlab.com/popsulfr/steamos-btrfs)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/jupiter-hw-support-btrfs/status_image/last_build.png?)|
|[mangohud](https://github.com/flightlessmango/MangoHud)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite-multilib/package/mangohud/status_image/last_build.png?)|
|mesa|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite-multilib/package/mesa/status_image/last_build.png?)|
|powerbuttond|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/powerbuttond/status_image/last_build.png?)|
|[python3-hid](https://github.com/apmorton/pyhidapi)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/python3-hid/status_image/last_build.png?)|
|rmlint|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/rmlint/status_image/last_build.png?)|
|[ryzenadj](https://github.com/FlyGoat/RyzenAdj)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/ryzenadj/status_image/last_build.png?)|
|[sddm-sugar-steamOS](https://github.com/JiayuanWen/sddm-sugar-steamOS)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/sddm-sugar-steamOS/status_image/last_build.png?)|
|[sdgyrodsu](https://github.com/kmicki/SteamDeckGyroDSU)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/sdgyrodsu/status_image/last_build.png?)|
|[steam-patch](https://github.com/KyleGospo/steam-patch)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/steam-patch/status_image/last_build.png?)|
|steamdeck-dsp|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/steamdeck-dsp/status_image/last_build.png?)|
|steamdeck-gnome-presets|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/steamdeck-gnome-presets/status_image/last_build.png?)|
|steamdeck-kde-presets|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/steamdeck-kde-presets/status_image/last_build.png?)|
|steamdeck-kde-presets-desktop|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/steamdeck-kde-presets-desktop/status_image/last_build.png?)|
|steam_notif_daemon|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/steam_notif_daemon/status_image/last_build.png?)|
|udisks2|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/udisks2/status_image/last_build.png?)|
|vpower|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/vpower/status_image/last_build.png?)|
|wireplumber|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/bazzite/package/wireplumber/status_image/last_build.png?)|

Additionally, the following packages are used from other Copr repos:

|Package|Status|
|---|---|
|[gcadapter_oc-kmod](https://copr.fedorainfracloud.org/coprs/ublue-os/akmods/)|![Build Status](https://copr.fedorainfracloud.org/coprs/ublue-os/akmods/package/gcadapter_oc-kmod/status_image/last_build.png?)|
|[gnome-vrr](https://copr.fedorainfracloud.org/coprs/kylegospo/gnome-vrr/)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/gnome-vrr/package/mutter/status_image/last_build.png?)|
|[hl2linux-selinux](https://copr.fedorainfracloud.org/coprs/kylegospo/hl2linux-selinux/)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/hl2linux-selinux/package/hl2linux-selinux/status_image/last_build.png?)|
|[kernel-fsync](https://copr.fedorainfracloud.org/coprs/sentry/kernel-fsync/)|![Build Status](https://copr.fedorainfracloud.org/coprs/sentry/kernel-fsync/package/kernel/status_image/last_build.png?)|
|[latencyflex-vulkan-layer](https://copr.fedorainfracloud.org/coprs/kylegospo/LatencyFleX/)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/LatencyFleX/package/latencyflex-vulkan-layer/status_image/last_build.png?)|
|[noise-suppression-for-voice](https://copr.fedorainfracloud.org/coprs/ycollet/audinux/)|![Build Status](https://copr.fedorainfracloud.org/coprs/ycollet/audinux/package/noise-suppression-for-voice/status_image/last_build.png?)|
|[obs-vkcapture](https://copr.fedorainfracloud.org/coprs/kylegospo/obs-vkcapture/)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/obs-vkcapture/package/obs-vkcapture/status_image/last_build.png?)|
|[openrgb-kmod](https://copr.fedorainfracloud.org/coprs/ublue-os/akmods/)|![Build Status](https://copr.fedorainfracloud.org/coprs/ublue-os/akmods/package/openrgb-kmod/status_image/last_build.png?)|
|[rom-properties](https://copr.fedorainfracloud.org/coprs/kylegospo/rom-properties/)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/rom-properties/package/rom-properties/status_image/last_build.png?)|
|[steamdeck-kmod](https://copr.fedorainfracloud.org/coprs/ublue-os/akmods/)|![Build Status](https://copr.fedorainfracloud.org/coprs/ublue-os/akmods/package/jupiter-kmod/status_image/last_build.png?)|
|[system76-scheduler](https://copr.fedorainfracloud.org/coprs/kylegospo/system76-scheduler/)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/system76-scheduler/package/system76-scheduler/status_image/last_build.png?)|
|[wallpaper-engine-kde-plugin](https://copr.fedorainfracloud.org/coprs/kylegospo/wallpaper-engine-kde-plugin/)|![Build Status](https://copr.fedorainfracloud.org/coprs/kylegospo/wallpaper-engine-kde-plugin/package/wallpaper-engine-kde-plugin/status_image/last_build.png?)|

## Verification

These images are signed with sigstore's [cosign](https://docs.sigstore.dev/cosign/overview/). You can verify the signature by downloading the `cosign.pub` key from this repo and running the following command:

```bash
cosign verify --key cosign.pub ghcr.io/ublue-os/bazzite
```

### Contributor Metrics

![Bazzite](https://repobeats.axiom.co/api/embed/86b500d79c613015ad16f56df76c8e13f3fd98ae.svg "Repobeats analytics image")

## Special Thanks

Bazzite is a community effort and wouldn't exist without everyone's support. Below are some of the people who've helped us along the way:

- [rei.svg](https://discord.com/users/rei.svg) - For creating our logo and overall branding.
- [evlaV](https://gitlab.com/evlaV) - For making Valve's code available and for being [this person](https://xkcd.com/2347/).
- [ChimeraOS](https://chimeraos.org/) - For gamescope-session and for valuable support along the way.
- [Jovian-NixOS](https://github.com/Jovian-Experiments) - For supporting us with technical issues and for creating a similar project. Seriously, go check it out. It's our Nix-based cousin.
- [sentry](https://copr.fedorainfracloud.org/coprs/sentry/) - For assistance with needed kernel patches.
- [Steam Deck Homebrew](https://deckbrew.xyz) - For choosing to support distributions other than SteamOS despite the extra work, and a special thanks to [PartyWumpus](https://github.com/PartyWumpus) for getting Decky Loader working with SELinux for us.
- [cyrv6737](https://github.com/cyrv6737) - For the initial inspiration and the base that became bazzite-arch.

## Build Your Own

Bazzite is built entirely in GitHub and creating your own custom version of it is as easy as forking this repository, adding a private signing key, and enabling GitHub actions.

[Familiarize yourself](https://docs.github.com/en/actions/security-guides/encrypted-secrets) on keeping secrets in github. You'll need to [generate a new keypair](https://docs.sigstore.dev/cosign/overview/) with cosign. The public key can be in your public repo <sub><sup>(Your users need it to check the signatures)</sup></sub>, and you can paste the private key in `Settings -> Secrets -> Actions` with the name `SIGNING_SECRET`.

We also ship a config for the popular [pull app](https://github.com/apps/pull) if you'd like to keep your fork in sync with upstream. Enable this app on your repo to keep track of Bazzite changes while also making your own modifications.

## Join The Community

You can find us on the [Universal Blue Discord](https://discord.gg/f8MUghG5PB).

You can also discuss Bazzite on our [Discourse](https://universal-blue.discourse.group/c/bazzite/5) and find additional [documentation](https://universal-blue.discourse.group/docs?category=5) surrounding the project too.
