# What is GladLive?

GladLive is network service comparable to Xboxlive or Steam for .Net applications. It's designed for distributed use with an emphasis on scalability. It provides core serives any online game requires such as:
  - Authentication*
  - Patching*
  - Profiles*
  - Lobby*
  - Chat (voice/message)
  - Matchmaking
  - Web*

(* denotes the service already exists or is partially implemented)

# What can GladLive do for me?

## How does GladLive work?

GladLive is primarily based on HTTP and the new crossplatform ASP core platform. The choice of HTTP was simply due to the availablity of technologies that allow HTTP to scale and the ability to utilize the same services to service Web requests.

Yes, that's right. GladLive can function in your application/game **and** service your web back-end and front-end needs in a single application.

### Modules

GladLive is built using a module/plugin system that allows users to register their desired modules with a skeleton service. Registering these modules/plugins in the application's configuration files allows you to turn applications into whatever you desire. You could built one application per web service or consolidate all modules on a single monolithic application (though not recommended).

##Licensing

This project is licensed under the MIT license with the additional requirement of adding the GladLive splashscreen to your product.
