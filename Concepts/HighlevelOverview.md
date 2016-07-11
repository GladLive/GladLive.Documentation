## GladLive High-level Overview

GladLive is a system where connected clients flow through linearly in several differen phases. These phases are spread across several different GladLive services.

### Phase 1

Phase 1 for the GladLive system begins with the GladLive Launcher that client's use to execute and patch their game.

GladLive Launcher Repo: [TBA]

GladLive Patching System: [TBA]

GladLive Patch Server: [TBA]

The GladLive launcher has two branches. A WPF branch for our main Windows target as well as a Monoforms branch for Mono platforms such as Mac or Linux. Although not yet implemented Patching will be done with simple version checking, if a 3rd party service isn't used, and patches will go over a GladNet2 HTTP client found here https://github.com/HelloKitty/GladNet.ASP.Client . This HTTP client will connect to the GladLive.Patch.ASP server which will provide patching payloads signed with a cert. For information on cert handling and RSA signing see https://github.com/GladLive/GladLive.Security.Common and the tool we use to generate client-side certs here https://github.com/GladLive/GladLive.Security.RSAGen .

If the game client for the game the user wants to play is up-to-date the user will be allowed to launch the game client.

### Phase 2
