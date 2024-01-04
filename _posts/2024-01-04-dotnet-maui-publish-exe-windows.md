## Publishing a .NET MAUI App as a Standalone EXE for Windows

.NET MAUI is typically designed for release as an MSIX package using a signed certificate and publishing to the Microsoft Store. However, in my case, I needed to release my MAUI project as an EXE because this application was an in-house application for Windows devices.


1. Open Visual Studio 2022 (or your IDE)
2. Right click on the project and Open in Terminal
3. Run the following command in the developer terminal

```powershell
dotnet publish -f net8.0-windows10.0.19041.0 -c Release -p:WindowsPackageType=None
```


* `dotnet publish`: This is the .NET CLI command used to publish .NET applications.
* `-f net8.0-windows10.0.19041.0`: This specifies the target framework and version. 
* `-c Release`: This sets the configuration to Release mode, which optimises the output for production.
* `-p:WindowsPackageType=None`: This specifies the package type is none which will produce a standalone EXE for our output

> [!NOTE]
> You may need to update the `net8.0-windows10.0.19041.0` to what your project is referencing.