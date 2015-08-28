DnxDemo
======

Use DNX to create and run a .NET 5 Core console application without Visual Studio.

If you don't have DNVM/DNX installed already, download and run the DNVM install script first by running the following from an administrator command prompt:

@powershell -NoProfile -ExecutionPolicy unrestricted -Command "&{$Branch='dev';iex ((new-object net.webclient).DownloadString('https://raw.githubusercontent.com/aspnet/Home/dev/dnvminstall.ps1'))}"

Then exit and re-enter the command shell to set environment variables. Run "dnvm" which will prompt you to setup the DNX runtime environment.

By default, the "clr x86" environment is installed, but we want the "coreclr x86" environment to be installed and used as the default, so run the command:

dnvm upgrade -r coreclr -arch x86

Navigate to the GitHub project directory for DnxDemo and run "dnu restore" which will read the project.json file and use NuGet to download the necessary packages for the application.

Now execute the application with "dnx . runme" and you have successfully run a cross platform .NET program with no dependencies on .NET runtime or Visual Studio being installed!
