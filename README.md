# ALiWa - Alias Light Wallet
[![Latest release](https://img.shields.io/github/v/release/aliascash/aliwa?label=Release&color=%2300bf00)](https://github.com/aliascash/aliwa/releases/latest)
[![Build Status Master](https://github.com/aliascash/aliwa/actions/workflows/build-master.yml/badge.svg)](https://github.com/aliascash/aliwa/actions)
[![Latest develop build](https://img.shields.io/github/v/release/aliascash/aliwa?include_prereleases&label=Develop-Build)](https://github.com/aliascash/aliwa/releases)
[![Build Status Develop](https://github.com/aliascash/aliwa/actions/workflows/build-develop.yml/badge.svg)](https://github.com/aliascash/aliwa/actions)
[![Discord](https://img.shields.io/discord/426769724018524161?logo=discord)](https://discord.gg/ckkrb8m)
[![Reddit](https://img.shields.io/badge/reddit-join-orange?logo=reddit)](https://www.reddit.com/r/AliasCash/)

A light wallet for the [ALIAS](https://alias.cash/) cryptocurrency.

## Donations
The easiest way to contribute to the Alias Light Wallet: Donate with ALIAS! 

```
Public ALIAS address: SSq7CjsPzfanmCkcN9XhKHg7yMn3bXj8i5
Private ALIAS address: smYhZCsqgJdRkWB64GaLZ165HejRCL3tAkmDmxdCrG2McnuH7gReE3LjDoXLRqf3txrwiuE3BCpFFAADDbU1oYW4fr7y9MnU37U3AD
```

## WARNING: Experimental ALPHA Software
**Please put no funds on this wallet, you're not willing to lose.
Also don't restore from seeds which contains funds you're not willing to lose.**

## Download Binaries (public testnet)
ALiWa will be supported by all major Desktop and Mobile platforms.

* **Windows** - **macOS** - **Linux DEB** - **Linux RPM**: [See latest release](https://github.com/aliascash/aliwa/releases/latest)
* Mobile: Android & iOS under [aliwa-mobile](https://github.com/dynamiccreator/aliwa-mobile)

# Build

## Windows

### Requirements

* C/C++ Compiler
* Node.js
* Python
* Git 

**It is recommended to install VisualStudio and select the above packages at the Installation process.**
(I believe everything but Git can be selected there)

### Preparation Steps

To build on Windows it is required to open a powershell as administrator and give "RemoteSigned" rights.

To do this: 
1. Open a power shell.
2. `Start-Process powershell -Verb runAs`
3. Confirm
4. In admin Power shell: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned`
5. Confirm with Yes

Now you're able to build on windows!

### Building Steps

**Step 2 and 3 are only required once**

1. `npm init -y`
2. `npm i --save-dev electron`
3. `npm i -g @electron-forge/cli` (install electron-forge)
4. `electron-forge import`
5. To setup the ALiWa icon follow the **APP ICON INSTRUCTIONS** from the file [confg package](confg%20package)
6. `npm install`
7. `npm run make`
8. Download [Tor.libraries.Win64.zip](https://github.com/aliascash/resources/blob/master/resources/Tor.libraries.Win64.zip) from the [Alias resources repository](https://github.com/aliascash/resources/tree/master/resources)
9. Unzip it into the build folder `out/ALiWa-win32-x64`, where `ALiWa.exe is located.
10. Zip folder `out/ALiWa-win32-x64` to create a simple archive with all required files.

With [Inno Setup](https://jrsoftware.org/isinfo.php) and by using the configuration file [inno-setup.iss](), you're able to build an easy to use installer:

```
iscc inno-setup.iss
```

### Windows 32 bit

Use the steps above but instead of step 7 use these steps:

7a. `install --save-dev electron-packager` (only once)

7b. `npx electron-packager . ALiWa-32 --platform=win32 --arch=ia32 --icon=view_resources/img/aliwa_light.ico`

## macOS

### Requirements

* Xcode & Xcode Comand Line Tools
* Node.js
* Git 

### Building Steps

**Step 2 and 3 are only required once**

1. `npm init -y`
2. `npm i --save-dev electron`
3. `npm i -g @electron-forge/cli` (install electron-forge)
4. `electron-forge import`
5. To setup the ALiWa icon follow the **APP ICON INSTRUCTIONS** from the file [confg package](confg%20package)
6. `npm install`
7. `npm run make`
8. Download [Tor.libraries.MacOS.zip](https://github.com/aliascash/resources/blob/master/resources/Tor.libraries.MacOS.zip) from the [Alias resources repository](https://github.com/aliascash/resources/tree/master/resources)
9. Unzip it into the build folder `out/ALiWa-darwin-x64/ALiWa.app`.
10. Zip folder `out/ALiWa-darwin-x64` to create a simple archive with all required files.

## Linux

### Requirements

* Node.js >=12.0.0
* Git
* Tor (Only for getting a connection running the app)

### Building Steps

**Step 2 and 3 are only required once**

1. `npm init -y`
2. `npm i --save-dev electron`
3. `npm i -g @electron-forge/cli` (install electron-forge)
4. `electron-forge import`
5. To setup the ALiWa icon follow the **APP ICON INSTRUCTIONS** from the file [confg package](confg%20package)
6. `npm run make`
