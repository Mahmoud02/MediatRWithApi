# MediatRWithApi
**This repo presents a discussion of how we can use MediatR in ASP.Net Core applications.** 

## MediatR
is an open source project and an implementation of the mediator design pattern. \
MediatR Pattern/Library is used to reduce dependencies between objects.\
It allows in-process messaging,but it will not allow direct communication between objects. \
Instead of this it forces to communicate via MediatR only. \
such as classes that don't have dependencies on each other, that's why they are less coupled. \


### 1-Create ASP.Net Core Project.
### 2-Install MediatR in your ASP.Net Core project
installing the following NuGet packages. \
MediatR \
MediatR.Extensions.Microsoft.DependencyInjection \
### 3-Configure MediatR in ASP.Net Core.
```c#
   public void ConfigureServices(IServiceCollection services)
        {
            //
            services.AddMediatR(typeof(Startup));
        }
```
## How mediator will work with the API Controller?
<img src="https://user-images.githubusercontent.com/18700494/109400136-aa366180-794f-11eb-9ce8-51ca5abe6c77.png" /> \
1-We're going to use an ASP.NET Web API Controller, which has a **mediator object** provided by the MediatR library.  \
2-The API Controller will pass a **RequestQuery object** into the mediator, and the mediator coordinates the logic of what to do next.  \
3-it will pick the **correct handler** that should be invoked for the current RequestQuery object.  \
4-The handler will perform the primary business logic to process the request, and it'll return a **response message** object to the mediator  \
5-which the mediator will **pass back** to the API Controller to be returned.  \

