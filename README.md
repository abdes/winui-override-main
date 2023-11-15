# Override `Main` in a WinUI Application

I was writing a WinUI 3 application that uses the [Entity
Framework](https://learn.microsoft.com/en-us/ef/) and the [Microsoft Hosting
Extensions](https://learn.microsoft.com/en-us/dotnet/api/microsoft.extensions.hosting?view=dotnet-plat-ext-7.0)
for IoC.

My migrations were not working. After a lot of troubleshooting I figured out
that the `EF` migrations tool has some specific assumptions on the order of
initializing the `Host`, the `Services` and the `Application` itself. Such fine
grained control is not possible using the default generated XAML entry point.

> ➡ How to properly override the default generated XAML entry point?
