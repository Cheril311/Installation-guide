<h1> VS Code </h1>
VS Code is a text editor developed by Microsoft with many features like text highlighting and support for many languages<br>

# Table of contents
  1. [Download VS code](#download)
  2. [Setting Up](#set)<br>
      a. [Windows](#windows) <br>
      b. [Mac](#mac) <br>
      c. [Linux](#linux) <br>
  3. [C++ using VSc](#cpp) <br>
## Download VS code <a name = "download"></a>
Click the download option below your respective operating system here:
https://code.visualstudio.com/Download
<br></br>
## How big is VS Code? 
VS Code is < 100 MB and has a disk footprint of less than 200 MB, so you can quickly install VS Code and try it out.

## Setting up VS Code <a name = "set"></a>

### Windows:<a name = "windows"></a>
Installation
1)	Download the Visual Studio Code installer for Windows.
2)	Once it is downloaded, run the installer (VSCodeUserSetup-{version}.exe).
3)	By default, VS Code is installed under C:\users\{username}\AppData\Local\Programs\Microsoft VS Code.
4)	Type ‘code .’ in your command prompt to open vs code 

*Alternatively, you can also download a Zip archive, extract it and run Code from there.

Note: .NET Framework 4.5.2 or higher is required for VS Code. If you are using Windows 7, make sure you have at least .NET Framework 4.5.2 installed. You can check your version of .NET Framework using this command in command prompt:

```python
reg query "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\full" /v version" 
```
### Mac OS <a name = "mac"></a>
Installation
1)	Download Visual Studio Code for macOS.
2)	Open the browser's download list and locate the downloaded archive.
3)	Select the 'magnifying glass' icon to open the archive in Finder.
4)	Drag Visual Studio Code.app to the Applications folder, making it available in the macOS Launchpad.
5)	Add VS Code to your Dock by right-clicking on the icon to bring up the context menu and choosing Options, Keep in Dock

<h4>Launching from the command line</h4>
You can also run VS Code from the terminal by typing 'code' after adding it to the path:<br>
1.	 Launch VS Code. <br>
2.	 Open the Command Palette (Cmd+Shift+P) and type 'shell command' to find the Shell Command: Install 'code' command in PATH command.
<img src= "https://code.visualstudio.com/assets/docs/setup/mac/shell-command.png"> 
3. Restart the terminal for the new $PATH value to take effect. You'll be able to type 'code .' in any folder to start editing files in that folder.

### Linux <a name = "linux"></a>
<h4>Snap</h4>
Visual Studio Code is officially distributed as a Snap package in the Snap Store<br>
You can install it by running:<br>



```python

 sudo snap install --classic code # or code-insiders                       
```
Once installed, the Snap daemon will take care of automatically updating VS Code in the background. You will get an in-product update notification whenever a new update is available.

<h4>Debian and Ubuntu based distributions</h4>
The easiest way to install Visual Studio Code for Debian/Ubuntu based distributions is to download and install the .deb package (64-bit), either through the graphical software center if it's available, or through the command line with:

```python

sudo apt install ./<file>.deb

# If you're on an older Linux distribution, you will need to run this instead:
# sudo dpkg -i <file>.deb
# sudo apt-get install -f # Install dependencies
```
Note that other binaries are also available on the VS Code download page.

Installing the .deb package will automatically install the apt repository and signing key to enable auto-updating using the system's package manager. Alternatively, the repository and key can also be installed manually with the following script:

```python
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
rm -f packages.microsoft.gpg
```
Then update the package cache and install the package using:
```python
sudo apt install apt-transport-https
sudo apt update
sudo apt install code # or code-insiders
```

## VSC for C++ <a name = "cpp"></a>
C/C++ support for Visual Studio Code is provided by a Microsoft C/C++ extension to enable cross-platform C and C++ development on Windows, Linux, and macOS.

<img src =  "https://code.visualstudio.com/assets/docs/languages/cpp/cpp-extension.png">
<h4>Install the extension</h4>
<ol>
 <li>Open VS Code.</li>
<li>Select the Extensions view icon on the Activity bar or use the keyboard shortcut (Ctrl+Shift+X).</li>
 <li>Search for 'C++'.</li>
 <li>Select Install.</li>
 </ol>

<img src = "https://code.visualstudio.com/assets/docs/languages/cpp/search-cpp-extension.png">

<h4>Install a compiler</h4>
C++ is a compiled language meaning your program's source code must be translated (compiled) before it can be run on your computer. The VSc C/C++ extension does not include a C++ compiler or debugger. You will need to install these tools or use those already installed on your computer.

Some platforms, such as Linux or macOS, have a C++ compiler already installed. Most Linux distributions have the GNU Compiler Collection (GCC) installed and macOS users can get the Clang tools with Xcode

<h4>Check if you have a compiler installed</h4>
Make sure your compiler executable is in your platform path (%PATH on Windows, $PATH on Linux and macOS) so that the C/C++ extension can find it. You can check availability of your C++ tools by opening the Integrated Terminal (Ctrl+`) in VS Code and trying to directly run the compiler.<br>
Checking for the GCC compiler g++:

```python
g++ --version
```

Checking for the Clang compiler clang:

```python
clang --version
```

If you don't have a compiler installed, in the example below, we describe how to install the Minimalist GNU for Windows (MinGW) C++ tools (compiler and debugger). MinGW is a popular, free toolset for Windows.

### Example: Install MinGW-x64
We will install Mingw-w64 via the SourceForge website. You can use this link https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/installer/mingw-w64-install.exe/download to download the Windows Mingw-w64 installer.

  1.Run the installer, which should be named mingw-w64-install.exe in your Download folder
  <img src = "https://code.visualstudio.com/assets/docs/languages/cpp/welcome-mingw-w64.png" height = "300">
 
 2.For Architecture select x86_64 and then select Next.
  
  <img src = "https://code.visualstudio.com/assets/docs/languages/cpp/choose-x86-64.png" height = "300">
  
 3. On the Installation Folder page, use the default location for the Destination folder. Copy the location as you will need it later.
 
 4. Select Next to start the installation.

<h3>Add the MinGW compiler to your path</h3>
Add the path to your Mingw-w64 bin folder to the Windows PATH environment variable by using the following steps:

  1. In the Windows search bar, type 'settings' to open your Windows Settings.<br>
  2. Search for Edit environment variables for your account.<br>
  3. Choose the Path variable and then select Edit.<br>
  4. Select New and add the Mingw-w64 destination folder path, with \mingw64\bin appended, to the system path. The exact path depends on which version of Mingw-w64 you have installed and where you installed it. If you used the settings above to install Mingw-w64, then add this to the path: <em>"C:\Program Files\mingw-w64\x86_64-8.1.0-posix-seh-rt_v6-rev0\mingw64\bin."</em><br>
  5. Select OK to save the updated PATH. You will need to reopen any console windows for the new PATH location to be available.

To check that your Mingw-w64 tools are correctly installed and available, open a new Command Prompt and type:

```python
g++ --version
gdb --version
```
If you don't see the expected output or g++ or gdb is not a recognized command, check your installation <b>(Windows Control Panel > Programs > Programs and Features)</b> and make sure your PATH entry matches the Mingw-w64 binary location where the compiler tools are located.
