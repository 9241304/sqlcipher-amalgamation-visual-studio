## Make sqlite/sqlcipher amalgamation using Visual Studio Command Prompt

### Prerequisites
1. Download and install Tcl ([recommended link](http://http://www.magicsplat.com/tcl-installer/index.html))
2. Add tcl tools to PATH. You can skip this step, but make sure you made SET "PATH=%PATH%;c:\path\to\tcl\tools" in Visual Studio Command Prompt

### Build amalgamation
1. Open the Visual Studio Command Prompt (Tools -> Command Line -> Developer Command Prompt)
2. cd to your Projects or SDKs folder (e.g. C:\SDK)
3. Clone sqlcipher (or sqlite3) repository 
`> git clone git@github.com:sqlcipher/sqlcipher.git`
4. cd to cloned repository and make .am folder and cd to created folder
`> cd sqlcipher`
`> mkdir .am`
`> cd .am`
5. Run amalgamation
`nmake /f ../Makefile.msc sqlite3.c TOP=..`

Done! Now you can use amalgamation in your project. **Don`t forget add compile definitions (SQLITE_HAS_CODEC) and SSL libraries to your project**, otherwise you will get regular sqlite3 functionality