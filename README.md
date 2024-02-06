# Melissa - MatchUp Object Global Windows Dotnet

## Purpose
This code showcases the Melissa MatchUp Object Global using C#.

Please feel free to copy or embed this code to your own project. Happy coding!

For the latest Melissa MatchUp Object Global release notes, please visit: https://releasenotes.melissa.com/on-premise-api/matchup-object-global/

For further details, please visit: https://wiki.melissadata.com/index.php?title=MatchUp_Object:Reference

The console will ask the user for:

- A txt file that contains global data you would like to matchup 
- A txt file that contains US data you would like to matchup

And return 

- A txt file of global duplicate groups
- A txt file of US duplicate groups

## Tested Environments
- Windows 10 64-bit .NET 7.0, Powershell 5.1
- Melissa data files for 2024-Q1

## Required File(s) and Programs

#### Binaries
This is the c++ code of the Melissa Object.

- mdMatchup.dll
- mdGlobalParse.dll

#### Data File(s)
- icudt52l.dat
- mdMatchup.dat
- mdMatchup.mc
- mdMatchup.sac
- mdMatchup.cfg

## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

#### Install the Dotnet Core SDK
Before starting, make sure that the .NET 7.0 SDK has been correctly installed on your machine (If you have Visual Studio installed, you most likely have it already). If you are unsure, you can check by opening a command prompt window and typing the following:

`dotnet --list-sdks`

If the .NET 7.0 SDK is already installed, you should see it in the following list:

![alt text](/screenshots/dotnet_output.png)

As long as the above list contains version `7.0.xxx` (underlined in red), then you can skip to the next step. If your list does not contain version 7.0, or you get any kind of error message, then you will need to download and install the .NET 7.0 SDK from the Microsoft website.

To download, follow this link: https://dotnet.microsoft.com/en-us/download/dotnet

Select `.NET 7.0` and you will be navigated to the download page.

Click and download the `x64` SDK installer for your operating system.

(IMPORTANT: Make sure you download the SDK, NOT the runtime. the SDK contains both the runtime as well as the tools needed to build the project.)

![alt text](/screenshots/net7.png)

Once clicked, your web browser will begin downloading an installer for the SDK. Run the installer and follow all of the prompts to complete the installation (your computer may ask you to restart before you can continue). Once all of that is done, you should be able to verify that the SDK is installed with the `dotnet --list-sdks` command.

#### Set up Powershell settings
If running Powershell for the first time, you will need to run this command in the Powershell console: `Set-ExecutionPolicy RemoteSigned`.
The console will then prompt you with the following warning shown in the image below. 
 - Enter `'A'`. 
    - If successful, the console will not output any messages. (You may need to run Powershell as administrator to enforce this setting).

 ![alt text](/screenshots/powershell_executionpolicy.png)

----------------------------------------

#### Download this project
```
$ git clone https://github.com/MelissaData/MatchUpObjectGlobal-Dotnet
$ cd MatchUpObjectGlobal-Dotnet
```

#### Set up Melissa Updater 
Melissa Updater is a CLI application allowing the user to update their Melissa applications/data. 

- Download Melissa Updater here: <https://releases.melissadata.net/Download/Library/WINDOWS/NET/ANY/latest/MelissaUpdater.exe>
- Create a folder within the cloned repo called `MelissaUpdater`.
- Put `MelissaUpdater.exe` in `MelissaUpdater` folder you just created.

----------------------------------------

#### Different ways to get data file(s)
1.  Using Melissa Updater
    - It will handle all of the data download/path and dll(s) for you. 
2.  If you already have the latest zip, you can find the data file(s) and dll(s) in there
    - Use the location of where you copied/installed the data and update the "$DataPath" variable in the powershell script.
    - Copy all the dll(s) mentioned above into the `MelissaMatchupObjectGlobalWindowsDotnet` project folder.

## Run Powershell Script
Parameters:
- -global: a test global txt file
- -us: a test US txt file

  These are convenient when you want to get results for specific txt files in one run instead of testing multiple txt files in interactive mode.

- -license (optional): a license string to test the MatchUp Object Global
- -quiet (optional): add to the command if you do not want to get any console output from the Melissa Updater

  When you have modified the script to match your data location, let's run the script. There are two modes:
- Interactive 

	The script will prompt the user for a global txt file and a US txt file, then use the provided txt files to test MatchUp Object Global.  For example:
    ```
    $ .\MelissaMatchupObjectGlobalWindowsDotnet.ps1
    ```
    For quiet mode:
    ```
    $ .\MelissaMatchupObjectGlobalWindowsDotnet.ps1 -quiet
    ```
- Command Line 

    You can pass a global txt file, US txt file, and a license string into the ```-global```, ```-us```, and ```-license``` parameters respectively to test MatchUp Object Global. For example:
    ```
    $ .\MelissaMatchupObjectGlobalWindowsDotnet.ps1 -global "MelissaMatchupGlobalSampleInput.txt" -us "MelissaMatchupUSSampleInput.txt"
    $ .\MelissaMatchupObjectGlobalWindowsDotnet.ps1 -global "MelissaMatchupGlobalSampleInput.txt" -us "MelissaMatchupUSSampleInput.txt" -license "<your_license_string>"
    ```
    For quiet mode:
    ```
    $ .\MelissaMatchupObjectGlobalWindowsDotnet.ps1 -global "MelissaMatchupGlobalSampleInput.txt" -us "MelissaMatchupUSSampleInput.txt" -quiet
    $ .\MelissaMatchupObjectGlobalWindowsDotnet.ps1 -global "MelissaMatchupGlobalSampleInput.txt" -us "MelissaMatchupUSSampleInput.txt" -license "<your_license_string>" -quiet
    ```
This is the expected output from a successful setup for interactive mode:

![alt text](/screenshots/output.png)

## Contact Us
For free technical support, please call us at 800-MELISSA ext. 4 (800-635-4772 ext. 4) or email us at tech@melissa.com.

To purchase this product, contact the Melissa sales department at 800-MELISSA ext. 3 (800-635-4772 ext. 3).
