# lonewrt-build

Build a [lonewrt](https://github.com/DamianPala/lonewrt) router image on GitHub, with no Linux machine.
lonewrt is OpenWrt firmware for the ZTE MF289F LTE router.
This repository is a template: it holds one workflow, which fetches a lonewrt release, builds an image from your profile, tests it and gives you the file to flash.

The image holds your Wi-Fi and root passwords and the other secrets of your profile.
So you use this template to make a **private** repository of your own.
A run in a public repository stops before it builds anything, because every signed-in GitHub user can download the files of a public repository's run.

## How to build

1. Click **Use this template** > **Create a new repository**, and choose **Private**.
2. Make your profile in the configurator of lonewrt (linked from [its README](https://github.com/DamianPala/lonewrt#readme)). Set both passwords in it: `WIFI_KEY`, and `ROOT_PASSWORD` or `ROOT_PASSWORD_HASH`. A run draws none, so that every run gives the same passwords. Keep the saved profile file, it holds them.
   Then in your new repository open **Settings > Secrets and variables > Actions > New repository secret**, name it `LW_PROFILE` and paste the whole text of the profile as its value.
3. Open **Actions > build > Run workflow**. Fill in the **version** of lonewrt to build (empty means the newest release) and the profile **name** (`router` is fine). Leave **test** unticked.
4. When the run is green, open it and download the artifact from the bottom of the page. **It stays for 7 days**, and the summary of the run names the last day. Unzip it: you get `router-sysupgrade.bin` and `router.manifest`.

Then flash the image and read the hints for the person who gets the router, in [lonewrt's README](https://github.com/DamianPala/lonewrt#after-flashing).

## Good to know

- To move to a newer lonewrt, run the workflow again with the new version. The steps of a run come with the release, so you never need to update this repository.
- If a run stops, its message names the problem: a missing secret, a profile key that is wrong (never its value), an empty password, or a failed test. Nothing is uploaded then.
- The **test** box is for trying the workflow in a public repository: it ignores your secret and builds made-up values. Do not flash that image. In a private repository it changes nothing.
- A run downloads, on GitHub's machine: the lonewrt release from GitHub, the OpenWrt ImageBuilder and packages from downloads.openwrt.org, two extra packages from GitHub and dl.eko.one.pl, and build tools from Ubuntu's package mirrors. lonewrt checks every download except the Ubuntu ones against a sha256 it pins. Your profile goes nowhere but into the image, and the image only into the run's download.
- Everyone who can read your repository can download the image while it is kept. Add no collaborators you would not give your router's passwords to.

## Project

Solo project, best effort, no response-time promise. Experimental, like lonewrt itself.
Built with AI coding agents under my direction.

- Bugs: every step of a build lives in lonewrt, so open the issue [there](https://github.com/DamianPala/lonewrt/issues), with the lonewrt version and the error line of the run. Paste no part of your profile.
- Security: use "Report a vulnerability" on the Security tab of [lonewrt](https://github.com/DamianPala/lonewrt/security), not a public issue.
- Pull requests for bug fixes are welcome; open an issue first for anything larger.

Licence: MIT, see [LICENSE](LICENSE).
