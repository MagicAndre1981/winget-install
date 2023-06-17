![image](https://github.com/asheroto/winget-installer/assets/49938263/e34c4551-291c-4862-8028-d35b4b7b0cec)

# Install winget from PowerShell

-   Install [winget-cli](https://github.com/microsoft/winget-cli) straight from PowerShell
-   Works on Windows 10, Windows 11, Server 2022
-   Does not work on Server 2019
-   Always gets the latest version of `winget`

## Script Functionality

-   Latest version of [Microsoft.UI.Xaml](https://www.nuget.org/packages/Microsoft.UI.Xaml/) is downloaded and installed.

-   [VCLibs](https://docs.microsoft.com/en-gb/troubleshoot/developer/visualstudio/cpp/libraries/c-runtime-packages-desktop-bridge#how-to-install-and-update-desktop-framework-packages) and [Xaml](https://www.nuget.org/packages/Microsoft.UI.Xaml/) are installed first

-   Processor architecture is determined for prerequisites

-   [VCLibs](https://docs.microsoft.com/en-gb/troubleshoot/developer/visualstudio/cpp/libraries/c-runtime-packages-desktop-bridge#how-to-install-and-update-desktop-framework-packages) is installed straight from the appx package

-   [Xaml](https://www.nuget.org/packages/Microsoft.UI.Xaml/) is installed by downloading the **nupkg**, extracting it, and installing the **appx** package

-   [winget-cli](https://github.com/microsoft/winget-cli) is then installed

-   User **PATH** variable is adjusted to include WindowsApps folder

-   Grabs the latest version of winget on each run

## Installation

### Method 1 - PowerShell Gallery

-   In PowerShell, type
```
Install-Script winget-install
```
- answer **Yes** to all prompts if asked

### Tip - How to trust PSGallery

If you want to trust PSGallery so you aren't prompted each time you run this command, you can type...

`Set-PSRepository -Name 'PSGallery' -InstallationPolicy Trusted`

### Method 2 - Download Locally and Run

-   Download `winget-install.ps1`

-   Run the script with `.\winget-install.ps1`

## Available Scripts

-   **winget-install.ps1**

    -   Unsigned script in the repo, signed script in releases

## Troubleshooting

-   If you receive an error message about the Appx module not being loaded, try using a different version of PowerShell (version 6 and 7 seem to be buggy still, but the native PowerShell version in Windows works)
- Open an issue if you run into a persistant problem.

## Contributing
If you're like to help develop this project: fork the repo. 😊