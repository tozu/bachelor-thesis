# Bachelor thesis

This repository contains the PDF of my thesis **Bluetooth Proximity as 2nd Factor**, which I submitted at the **University of Applied Sciences Upper Austria** during my enrollment as [**Mobile Computing**](https://www.fh-ooe.at/en/hagenberg-campus/studiengaenge/bachelor/mobile-computing/) student.

My task was to develop a solution which would allow to extend any arbitary login scheme with an additional authentication mechanism. The selected authentication mechanism is _Bluetooth_, which is known to only operate and be accessible within couple of meters (< 100m).

Therefore, this mechanism offers the authentication factor of 'something you have', by utilizing the Bluetooth device as additional constraint needed to complete the login scheme.

To utilize _Bluetooth_ as an addtional factor a daemon runs on a system which has a Bluetooth stack included. There a three different security levels available, where each level require more information has to be submitted and validated.

Security levels:
- Level 1 - Proximity only
- Level 2 - Proximity + OTP
- Level 3 - Proximity + OTP + HMAC

---
OTP - One-Time-Password

HMAC - Hash-based Message Authentication Code

## Implementation

Accompanying the thesis I implemented the neccessary daemon which would contiously query for Bluetooth devices and grants/denies access depending on the found device(s) and valid information submitted. Further, I developed various clients spanning different platforms, securing their login schemes.

- Daemon (GitHub repo: [**here**](https://github.com/tozu/ba-2fa-daemon/))

Clients:
- Windows (GitHub repo: [**here**](https://github.com/tozu/ba-2fa-windows-client/))
- Linux PAM (GitHub repo: [**here**](https://github.com/tozu/ba-2fa-linux-pam/))
- Firefox (GitHub repo: [**here**](https://github.com/tozu/ba-2fa-ff-extension/))
- Android auth./companion app (GitHub repo: [**here**](https://github.com/tozu/ba-2fa-authentication-tool/))

## Abstract (complete)

The goal of this bachelor thesis is to write a daemon, which detects the proximity of a Bluetooth device in order to verify that a certain action (e.g. an attempted login) is valid and performed by an authenticated user.

The authentication of the user is verified in two steps:
1. The user needs to provide the login credentials (“Something you know”)
2. The user needs to have an authentication device - in this case a Bluetooth device (“Something you have”)

This authentication process is called Two-factor authentication (2FA). With this bachelor thesis comes a background application (daemon) and three functional client implementations of a two-factor authentication with Bluetooth proximity sensing. One of the client implementations is an internet browser extension for Mozilla Firefox, which will add an additional security factor to the included password manager. The other implementation is a Linux PAM module, which adds a security component to the login scheme. The third client is a Windows Desktop client, which automatically locks the screen if the Bluetooth device isn’t nearby.

The thesis will cover besides the implementation of mentioned clients and daemon, a coverage and explanation of current already existing solutions of Two-factor authentication. Furthermore, it will present the usual operating places and limitations of Two-factor authentication. Note: The expression “second-factor authentication” is equal to “two factor authentication” and can be used interchangeably
