# What is GladLive?

GladLive is network service comparable to Xboxlive or Steam for .Net applications. It's designed for distributed use with an emphasis on scalability. It provides core serives any online game requires such as:
  - oAuth/JWT Authentication*
  - Patching
  - Profiles*
  - Lobby*
  - Chat (voice/message)
  - Matchmaking
  - Web*
  - TLS/HTTPS*

(* denotes the service already exists or is partially implemented)

# Tell me about those Services

**Authentication:** The GladLive authentication service is an oAuth2 service that issues signed JSON Web Tokens for authorization accross all other applications. This allows GladLive to be mostly stateless, loosely coupled and segregated.

**Profiles:** The GladLive Profile service provides a basic profile system. It services basic information requests about who other users are. This can be extended on a per-usecase basis.

**Lobby:** The GladLive Lobby module consists of a generic Lobby/Party system. It provides for the ability to implement several types of lobbies and parties. Currently there is an already implemented PeerToPeer lobby system module available for use. This is a typical setup that most FPS p2p games may have.

# What can GladLive do for me?

GladLive provides several services and features but the true potential of GladLive is its arcitecture and ease-of-use and the meta-features.

**GladLive Integration:** GladLive is a service where you can pick and choose what services and modules you run. This is due to the distributed nature of GladLive which relies on the JWT for identification. On top of this flexibility it utilizes a Unity3D HTTP client called GladNet. Integration of this client into your Unity3D project or .Net project is simple and doesn't need to be directly integration into your application's source. This makes adding additional GladLive services to your application, or removing them if you no longer want them, as simple as removing the libraries and modules.

**GladLive Scalability, Elasticity and Loadbalancing:** Have 10 players? No problem. GladLive can service their requests by running server applications on Mac/Linux/Windows on a home laptop with nearly no bandwidth requirement. No need to dedicated servers with a monthly fee. Have 10,000 players? GladLive is built with scalability in mind taking a stateless microservice approach. It utilizes ASP core's multithreaded async request handling you get the most throughput possible while still staying highlevel. The stateless nature of most of the GladLive applications allows you to dynamically scale and add server applications when demand rises or remove them when demand falls. This requires **NO** change in source code and many services such as AWS can help you do this automagically. 30,000 people decide to play your game out of the blue one day because a streamer is playing it? You're prepared to service them and retain them as users. Without GladLive and scalability you could lose thousands of potential users just because your service bit the dust during a load spike.

**GladLive Fault Tolerance:** GladLive is built in such a way to reduce gameplay disruption during failures as there is no single point of failure. The only critical service being the AuthenticationService is only needed to introduce new users to the GladLive network. Should a particular service outage occur, say the Profile service or Authentication service, other services will be unaffected. Users can continue to play their games but will not be able to access the disrupted services until the recovery but no other services will be affted. In many cases their gameplay will likely be completely unaffected if a Peer-To-Peer game. No two GladLive services depend on eachother so if users cannot chat due to a ChatService disruption they can still view profiles or join lobbies. This helps retain users during disasters and should positivwely affect the rentention of playerbases.

**Security:** GladLive utilizes industry standards for security without requiring users or developers to deal with it manually. Out-of-the-box GladLive supports TLS/HTTPS, hashes any passwords and uses modern JWT wuth request signing for authorization. GladLive is not susceptible to MITM attacks as certificate sigantures are verified on the client and this helps prevent traffic tampering too. GladLive puts security as a first priority in developing any service and actively prevents exploits common to insecure APIs such as packet spoofing to act as other players.

**Web/Website:** GladLive is primarily based on HTTP and the new crossplatform ASP core platform. The choice of HTTP was simply due to the availablity of technologies that allow HTTP to scale and the ability to utilize the same services to service Web requests. However, this means that GladLive also acts as a webservice and helps consolidate services into a central applications. No more code duplicate between your gameservers and your webservers. They are one-in-the-same and this should save you a considerable amount of time keeping feature parity between both your game and web.

## How does GladLive work?

### Modules

GladLive is built using a module/plugin system that allows users to register their desired modules with a skeleton service. Registering these modules/plugins in the application's configuration files allows you to turn applications into whatever you desire. You could built one application per web service or consolidate all modules on a single monolithic application (though not recommended).

## But what does GladLive cost me?

GladLive is licensed under MIT and therefore costs you $0 dollars. No licensing hassle, no concurrent user caps and no nonsense. GladLive and GladNet, the networking API GladLive is based on, is MIT licensed and open-source available for modification.

### How much does GladLive cost to run?

For most users GladLive will cost you nothing to run. With low bandwidth requires and the fact that it's essentially a webservice which doesn't even need to service js/httml/css it's easier to run than a basic website. You can run it on your old laptop if you only have a handful of users. Many far more demanding MMOs have run on lesser hardware than is available in your room right now.

With a low memory and CPU footprint GladLive can run on micro AWS instances which would handle more load than most games will ever see. For the same price of an Xboxlive monthly suscription you can run GladLive on industry grade cloud instances which is basically an XboxLive-like service. You may never even need to though.

##Licensing

This project is licensed under the MIT license with the additional requirement of adding the GladLive splashscreen to your product.
