# .NET 

## .NET Core vs .NET standard vs .NET framework
- **.NET Standard (library)**
  - Used for building libraries that can be referenced from all .NET implementations, such as .NET Framework, .NET Core and Xamarin.
  - Each implementation of the managed framework has its own set of Base class libraries. The Base class lib (BCL) contains classes such as exception handling, strings, XML, I/O, networking and collections.
  - .NET standard is an API specification that defines, for a given version, what Base Class Libraries (BCL) must be implemented. 
  - This standard allows developers to know there will be a consistent set of APIs they can rely on.
  - Framework Class Libraries (FCL) such as WPF, WCF, and ASP.NET are not part of the BCL, and therefore not included in the .NET standard.
  - Defines a set of APIs that .NET platforms agree to implement.
  - Any platform that implements a .NET standard is comptaible with libs that target that .NET standard.
  - One of those compatible platforms is .NET Core.
- **.NET Core**
  - A free, cross-platform, open source implementation of the managed framework.
  - .NET Core is a managed framework that is optimized for building console, cloud, ASP.NET Core, and UWPO applications
    - Used for building cross-platform console apps and ASP.NET Core Web apps and cloud services
  - It provides an implementation of .NET Standard for the Base Class Libraries.
  - Supports self-contained deployments.
    - You can containerize your application using Docker such that it has it's own copy of the .NET Core runtime.
    - This lets you run different applications on the same machine using different .NET Core versions without them interfering with each other.
  - Supports the following applications:
    1. Console
    2. ASP.NET Core
    3. Cloud
    4. Universal Windows Platform (UWP)
    5. Windows Forms (.NET Core 3)
    6. Windows Presentation Foundation (WPF) - (.NET Core 3)
  - .NET Core is not considered a Windows component, therefore updates come as NuGet packages, not through windows updates.
  - Applications can be associated with a particular .NET Core version and be updated individually.
  - **.NET Core CLI's main driver is called "dotnet"**
    - You can use it for all aspects of development, including creating, building, testing and packaging projects. 
  - **Use .NET Core for your server application when:**
    - You have cross-platform needs
    - Are targeting microservices
      - Azure Service Fabric (for complex microservices)
      - Azure App Service (for stateless microservices)
      - Microservices typically used with containers.
    - using Docker containers
    - need high-performance and scalable systems
    - need side-by-side .NET versions per application
- **.NET Framework**
  - The .NET framework is used for building desktop applications and ASP.NET applications (web apps) running on IIS. 
  - First managed framework released.
  - **Use .NET Framework for your server application when:**
    - Your app currently uses .NET Framework (recommendation is to extend instead of migrating).
    - Your app uses third-party .NET libraries or NuGet packages not available for .NET Core.
    - Your app uses .NET technologies that aren't available for .NET Core.
    - Your app uses a platform that doesn't support .NET Core.
- **Xamarin**
  - A managed framework used for building iOs, Android, and macOS desktop applications.
  - Used for building mobile applications for iOS and Android, as well as desktop apps for macOS.
  - A software compnay that provides developer with with tools to build cross-platform mobile applications.
  - **How does it work**
    - Xamarin converted entire existing Android and iOS SDK to C#
    - You can access the iOS or Andriod API in C# with Xamarin tools.
    - For the UI you can use original native methods to build the UI or you can use Xamarin.Forms, Forms let you build UI for different platforms all at once. Almost 100% code sharing if you decide to use Xamarin.Forms over Native UI technology.
      - Build the UI separately for different platforms and then bind the UI with the common code base
      - Builds actual native application UI, Below the platform specific UI code, is the shared C# code that calls the common codebase. 
    - Most difficult is connecting the UI to the code base. That can be done by strategies called Shared Project or Portable Class Libraries.
- References:
  - https://www.infoq.com/news/2017/10/dotnet-core-standard-difference
  - https://docs.microsoft.com/en-us/dotnet/standard/choosing-core-framework-server
  - https://msdn.microsoft.com/en-us/magazine/mt842506
  - https://www.thewindowsclub.com/what-is-xamarin-and-cross-platform-mobile-development
  - https://social.msdn.microsoft.com/Forums/vstudio/en-US/7035edc6-97fc-49ee-8eee-2fa4d040a63b/what-are-differences-between-net-framwork-net-standard-and-net-core?forum=clr
  - https://blogs.msdn.microsoft.com/dotnet/2017/08/14/announcing-net-standard-2-0/

## C# 8
- Features:
   - Using declarations have changed
   - Switch expressions
   - Fast in-box JSON writer and JSON Document
     - System.Text.Json.Utf8JsonWriter (30-80% faster than using Json.NET)
     - System.Text.Json.JsonDocument.
-  https://blogs.msdn.microsoft.com/dotnet/2019/01/29/announcing-net-core-3-preview-2/

## Definitions
- **Global Assembly Cache (GAC)**
  - A folder in Windows where all shared .NET assemblies reside. These assemblies can be shared by all applications executed on a system. A place to store code libraries so they're accessible to all applications running on the machine.
  - A way to keep DLLs globally accessible without worrying about conflicts (No more DLL hell)
  - Each architecture and version gets it's own place to live. 
  - Also gets its own way to browse it in Explorer, i.e. can go to C:\Windows\assembly which lists all the DLLs.

