# MediatRWithApi
**This repo presents a discussion of how we can use MediatR in ASP.Net Core applications.** \

## MediatR
is an open source project and an implementation of the mediator design pattern. \
MediatR Pattern/Library is used to reduce dependencies between objects.\
It allows in-process messaging,but it will not allow direct communication between objects. \
Instead of this it forces to communicate via MediatR only. \
such as classes that don't have dependencies on each other, that's why they are less coupled. \


### Create ASP.Net Core Project.
### Install MediatR in your ASP.Net Core project
installing the following NuGet packages.
MediatR/
MediatR.Extensions.Microsoft.DependencyInjection/
### Configure MediatR in ASP.Net Core.
```c#
   public void ConfigureServices(IServiceCollection services)
        {
            //
            services.AddMediatR(typeof(Startup));
        }
```
