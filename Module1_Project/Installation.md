# Installing Python on Windows

## Software Requirements

- A Windows 10 or Windows 11 computer.
- An internet connection to download the installer.
- Permission to install software on the computer. On a managed device, contact the administrator if installation is blocked.
- A web browser and Windows PowerShell or Windows Terminal.

No separate compiler or paid software is required for a standard Python installation.

## Installation Steps

1. Open the official Python downloads page: [python.org/downloads](https://www.python.org/downloads/).
2. Select the current stable Python 3 release for Windows. Choose the 64-bit installer for most modern Windows computers.
3. Open the downloaded installer.
4. On the first installer screen, select **Add python.exe to PATH**. This makes it easier to run Python from PowerShell.
5. Select **Install Now** for a standard installation. If Windows asks for permission, approve the installer if you are authorized to do so.
6. Wait for setup to finish, then select **Disable path length limit** if that option appears and you want to avoid Windows path-length restrictions.
7. Close and reopen PowerShell or Windows Terminal so it picks up the updated environment settings.

## Verification Steps

Open a new PowerShell window and run:

```powershell
py --version
```

The command should display the installed Python 3 version. Also check that Python can run a short statement:

```powershell
py -c "print('Python is installed and working.')"
```

Check that `pip`, Python's package installer, is available:

```powershell
py -m pip --version
```

If these commands display a version and the confirmation message, the installation is ready to use. The Windows Python launcher command `py` is generally available even when the `python` command is not on PATH.

## Troubleshooting

### `py` is not recognized

The launcher may not have been installed, or the terminal may have been open during installation. Close and reopen PowerShell, then try again. If it still fails, rerun the official installer and choose **Modify** or reinstall with the Python Launcher option enabled.

### `python` opens the Microsoft Store or is not recognized

Try `py` instead. If you specifically need the `python` command, confirm that **Add python.exe to PATH** was selected in the installer. Windows app execution aliases can also affect the `python` command; check **Settings > Apps > Advanced app settings > App execution aliases** and adjust the Python aliases if needed.

### Python reports an unexpected version

More than one Python installation may be present. Run `py -0p` to list versions and their locations. Use `py -3` to select a Python 3 installation, or specify a version such as `py -3.12` when that version is installed.

### `pip` is not available

Run `py -m ensurepip --upgrade`, followed by `py -m pip --version`. Using `py -m pip` helps ensure that packages are installed for the Python interpreter selected by the launcher.

### Installation is blocked or fails

Confirm that the installer came from python.org and that the download completed. On a work or school computer, installation may require administrator approval or an approved software portal. Contact the device administrator rather than bypassing those controls.
