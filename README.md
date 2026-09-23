[README.md](https://github.com/user-attachments/files/32561130/README.md)
# Carry B's AI — Windows personal profile build

This release adds a friendly first-run setup screen to the Windows desktop application. The screen asks for **Name**, **Surname**, **Country**, **City**, and **Education level**. The education menu includes Zimbabwe examination-oriented options for **ZIMSEC Primary Grade 7**, **ZIMSEC Ordinary Level (O-Level)**, and **ZIMSEC Advanced Level (A-Level)**, followed by vocational, certificate, diploma, undergraduate, postgraduate, and prefer-not-to-say options.

The profile is stored locally in the Electron application data directory for the current Windows account. It is used to personalise the HUD and is not automatically uploaded. Carry B's AI does not collect passwords, browser cookies, Google tokens, or account credentials. The profile can be reset from **HUD Config → Reset Local Profile**.

## Included Windows artifacts

`Carry-Bs-AI-1.0.0-installer.exe` is the normal installer. It creates Start Menu and desktop shortcuts using the futuristic Carry B's AI icon. `Carry-Bs-AI-1.0.0-portable.exe` can be run without installation.

## Python package

The `python` folder contains the bounded local support worker, optional OCR capability check, tests, and its own README. Python is not required for the main HUD. To run its checks on Windows, install Python 3 and execute:

```powershell
py -3 python\test_ocr_runtime.py
```

The Electron application invokes only the restricted worker actions; it does not provide unrestricted Python shell access. Do not run the application as Administrator unless you understand the security implications.

## Browser permissions

Personal Gmail, Google, and Google Play Store access remains explicit and allowlisted. The user grants each category in HUD Config, then Carry B's AI opens the approved page in the normal browser. Sign-in is completed by the user in the browser. The app does not bypass sign-in or read private credentials.

## Verification

This release was rebuilt with the first-run profile flow, the futuristic icon, the packaged Python support files, and the existing safe command controls. TypeScript checking and the full project test suite pass **46/46 tests**.
