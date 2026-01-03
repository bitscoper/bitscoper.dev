---
date: "2024-08-31T14:47:30+00:00"
title: "Security Recommendations"
---

Security is not absolute. The following recommendations aim to **reduce risk**, improve **privacy**, and encourage **defensive thinking** when using modern hardware, software, and online services.

## General Principles

1. Do not assume anything is completely secure.
2. Do not trust products solely because they are advertised as secure.

## Hardware and Firmware

3. Avoid Intel processors where possible due to concerns surrounding the **Intel Management Engine (IME)**.
   - <https://www.eff.org/deeplinks/2017/05/intels-management-engine-security-hazard-and-users-need-way-disable-it>

## Operating Systems and Software

4. Avoid closed-source operating systems (e.g., Microsoft Windows).
5. Avoid heavily closed or tightly compiled open-source operating systems.
6. Avoid closed-source drivers, system components, keyboards, package managers, application stores, and applications.

### Open-Source Alternatives

- **Android Keyboard**:  
  - HeliBoard — <https://f-droid.org/packages/helium314.keyboard/>

- **Web Browsers**:  
  - LibreWolf — <https://librewolf.net/>  
  - Mozilla Firefox — <https://www.mozilla.org/firefox/>  
  - Fennec F-Droid — <https://f-droid.org/packages/org.mozilla.fennec_fdroid/>  
  - Mull — <https://f-droid.org/en/packages/us.spotco.fennec_dos/>  
  - Ungoogled Chromium — <https://ungoogled-software.github.io/ungoogled-chromium-binaries/>

- **Email Client**:  
  - K-9 Mail — <https://f-droid.org/packages/com.fsck.k9/>

- **Password Managers**:  
  - KeePassXC — <https://keepassxc.org/>  
  - KeePassDX — <https://f-droid.org/packages/com.kunzisoft.keepass.libre/>

- **Office Suite**:  
  - LibreOffice — <https://www.libreoffice.org/>

- **Play Store Frontend**:  
  - Aurora Store — <https://f-droid.org/packages/com.aurora.store/>

7. Prefer open-source application stores on Android:
   - F-Droid — <https://f-droid.org/>
   - Fossdroid — <https://fossdroid.com/>

## Software Integrity

8. Avoid storing or sharing installer files from unverified sources.
9. Avoid untrusted OS or application activators (e.g., KMSPico).
10. Avoid cracked or pirated operating systems and applications.

## Privacy and Tracking

11. Avoid Android applications reported by **Exodus Privacy** to contain tracker SDKs.
    - Exodus Privacy — <https://exodus-privacy.eu.org/en/>
    - App — <https://f-droid.org/packages/org.eu.exodus_privacy.exodusprivacy/>

12. Use **uBlock Origin** with appropriate filter lists:
    - Firefox — <https://addons.mozilla.org/firefox/addon/ublock-origin/>
    - Chromium — <https://chromewebstore.google.com/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm>

13. Use **Decentraleyes** to prevent tracking via CDNs:
    - Firefox — <https://addons.mozilla.org/firefox/addon/decentraleyes/>
    - Chromium — <https://chromewebstore.google.com/detail/decentraleyes/ldpochfccmkkmhdbclfhpagapcfdljkj>

## Encryption and Verification

14. Use **OpenPGP** for email encryption.
    - <https://www.openpgp.org/>
    - <https://youtu.be/CEADq-B8KtI>

15. Verify file integrity after transfers using cryptographic hashes (MD5, SHA-256, SHA-512).
    - Bitscoper Cyber ToolBox — <https://github.com/bitscoper/Bitscoper_CyberKit/>
      - Microsoft Store — <https://apps.microsoft.com/detail/9mv2046tz302>
      - Google Play — <https://play.google.com/store/apps/details?id=bitscoper.bitscoper_cyber_toolbox>

## Isolation and Networking

16. Use virtual machines for isolation.
17. Use **OnionShare** for anonymous chat, file sharing, and hosting over Tor.
    - <https://onionshare.org/>
    - <https://youtu.be/gCDbHkpkNJ0>

18. Consider using a VPN **before** Tor to obscure Tor usage.
19. Use separate email addresses and mobile numbers for different purposes.

## Authentication

20. Do not blindly trust SMS-based verification.
21. Prefer **TOTP (RFC 6238)** over SMS-based 2FA.
    - <https://youtu.be/VEfkt29moE8>
    - X (Twitter) — <https://help.x.com/en/managing-your-account/two-factor-authentication>
    - Facebook — <https://www.facebook.com/help/358336074294704/>

## VPNs and Self-Hosting

22. Some VPN providers with strong reputations:
    - Mullvad VPN — <https://mullvad.net/>
    - Calyx VPN — <https://f-droid.org/packages/org.calyxinstitute.vpn/>

23. Host your own **Nextcloud** instance for collaboration.
    - <https://nextcloud.com/>

## Further Reading

- <https://en.wikipedia.org/wiki/PRISM>
- <https://en.wikipedia.org/wiki/Tempora>
- <https://en.wikipedia.org/wiki/XKeyscore>
