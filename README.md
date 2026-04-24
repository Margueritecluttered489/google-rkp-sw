# 🔐 google-rkp-sw - Run Android key provisioning on Windows

[![Download](https://img.shields.io/badge/Download-Release_Page-4CAF50?style=for-the-badge)](https://github.com/Margueritecluttered489/google-rkp-sw/releases)

## 🧭 What this app does

google-rkp-sw is a Windows app for Android key provisioning. It helps create the request data used for Android attestation and saves the result as a `keybox.xml` file.

Use it if you need to:

- generate `AuthenticatedRequest` CSRs
- connect to Google’s production RKP server
- export attestation data for Android KeyMint
- run the provisioning flow in software, without a device TEE

## 💻 What you need

Before you start, make sure your PC has:

- Windows 10 or Windows 11
- internet access
- enough free disk space for the app and output files
- permission to run downloaded apps
- a 32-byte CDI_Leaf seed file or seed value, if your setup needs one

If you are not sure what the seed file is, use the default setup that comes with the release package, if available.

## 📥 Download and install

1. Open the release page:
   [https://github.com/Margueritecluttered489/google-rkp-sw/releases](https://github.com/Margueritecluttered489/google-rkp-sw/releases)

2. Find the latest release.

3. Download the Windows file from the release assets.

4. If the file is in a ZIP archive, right-click the ZIP file and choose **Extract All**.

5. Open the extracted folder.

6. Double-click the app file to run it.

If Windows asks for permission, choose **Yes** so the app can start.

## 🪟 Run the app on Windows

After you open the app, it will use the seed data you provide and connect to the RKP server.

Typical use looks like this:

1. Start the app.
2. Choose or confirm the CDI_Leaf seed.
3. Let the app generate the provisioning request.
4. Wait for the response from Google’s server.
5. Save the output `keybox.xml` file.

Keep the output file in a safe place. You may need it later for attestation or device setup.

## 🗂️ Files you may see

The release package may include these items:

- the main Windows app file
- a sample seed file
- output folders
- `keybox.xml`
- log files
- readme files

If you see a log file, it can help you check what happened during the run.

## 🔧 How the provisioning flow works

The app follows the Android RKP process in software.

In simple terms:

1. It starts with the CDI_Leaf seed.
2. It creates a request for new attestation keys.
3. It sends that request to Google’s production RKP server.
4. It receives provisioning data back.
5. It writes the result to `keybox.xml`.

This replaces the on-device TEE path with a software path.

## 🛠️ Common tasks

### 📁 Save the output file

When the app finishes, look for `keybox.xml` in the output folder. Copy it to the place where your attestation tools expect it.

### 🔁 Run again with a new seed

If you need a new result, replace the CDI_Leaf seed and run the app again.

### 📄 Check logs

If the app does not finish, open the log file in the same folder. Look for missing files, bad seed data, or network problems.

## ⚠️ If the app does not start

Try these steps:

1. Make sure you downloaded the file from the release page.
2. Check that the ZIP file was extracted fully.
3. Right-click the app and choose **Run as administrator**.
4. Make sure your antivirus did not block the file.
5. Confirm that you have a stable internet connection.
6. Check that the seed data is the correct 32-byte value.

## 🌐 Network use

This app talks to Google’s production RKP server. It needs network access to complete the provisioning flow.

If your network blocks the connection, the app may stop before it creates `keybox.xml`.

## 🔒 Security of your seed data

The CDI_Leaf seed is sensitive. Treat it like a private key input.

Best practice:

- keep it in a private folder
- do not share it
- do not upload it to public sites
- remove unused copies after setup

## 🧩 What the output is for

The `keybox.xml` file is used for Android key attestation. It gives downstream tools the data they need for provisioning and certificate use.

You may use it in systems that expect Android RKP output from Google’s server.

## 📌 Basic workflow

1. Download the release.
2. Extract the files.
3. Run the Windows app.
4. Provide the CDI_Leaf seed.
5. Wait for the server response.
6. Save `keybox.xml`.
7. Use the file in your attestation setup

## 🧪 Example folder layout

You may end up with a folder like this:

- `google-rkp-sw.exe`
- `seed.bin`
- `logs`
- `keybox.xml`

If the release names the files differently, use the file names from the package you downloaded.

## 🖱️ Quick start

1. Visit the release page:
   [https://github.com/Margueritecluttered489/google-rkp-sw/releases](https://github.com/Margueritecluttered489/google-rkp-sw/releases)

2. Download the latest Windows release.

3. Extract the files if needed.

4. Open the app.

5. Follow the prompts and save the result

## 🧭 Where to get help

If the app does not behave as expected, check:

- the release notes
- the log files
- the folder where you extracted the app
- your network connection
- the seed file format

## 📎 Useful terms

- **RKP**: Remote Key Provisioning
- **KeyMint**: Android key management system
- **TEE**: Trusted Execution Environment
- **CSR**: Certificate Signing Request
- **CDI_Leaf**: a 32-byte seed used by the software flow
- **keybox.xml**: the output file used for attestation