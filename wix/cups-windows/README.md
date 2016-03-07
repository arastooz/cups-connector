# Windows Installer

## Build Requirements
The WIX toolset is required to build the Windows Installer file, the WIX toolset is required. 
It can be downloaded from http://wixtoolset.org.

## Build Instructions
Run candle.exe to build wixobj file from the wxs file:
candle.exe -arch x64 cups-connector.wxs

Run light.exe to build MSI file from the wixobj
light.exe -ext "C:\Program Files (x86)\WiX Toolset v3.10\bin\WixUIExtension.dll" cups-connector.wixobj

If the WIX toolset is installed to a different directory, use that directory path for the
UI extension dll.

If the built CUPS connector binaries are not in $GOPATH\bin, then add -dSourceDir=<Path> 
to the light.exe command line to specify where the files can be found.

If mingw64 is not installed to C:\msys64\mingw64, then use -dDependencyDir=<Path> 
to specify where it is installed.

## Installation Instructions
