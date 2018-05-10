# DeckHub

This is the Home repo for the DeckHubApp organization, which comprises multiple projects.

DeckHub is a [RendleLabs](https://rendlelabs.com) project with two aims:

1. Provide a useful set of tools for speakers, listeners and conference organizers to
engage with each other and share knowledge more effectively.
2. Act as a reference application for cloud-native [ASP.NET Core](https://www.asp.net),
with microservices, messaging, containerization, orchestration and so on.

# Projects

I'm working on adding a proper README to each project that details how they work and stuff.

- **[cli](https://github.com/DeckHubApp/cli)** -
is the command line tool for running presentations locally.
- **[Live](https://github.com/DeckHubApp/Live)** -
website (central one is running at [deckhub.app](https://deckhub.app)).
- **[Identity](https://github.com/DeckHubApp/Identity)** -
microsite to handle user authentication with [ASP.NET Identity](https://github.com/aspnet/Identity)
- **[Shows](https://github.com/DeckHubApp/Shows)** -
microservice for Shows.
- **[Questions](https://github.com/DeckHubApp/Questions)** -
microservice for Questions.
- **[Notes](https://github.com/DeckHubApp/Notes)** -
microservice for viewer Notes.
- **[Realtime](https://github.com/DeckHubApp/Realtime)** -
[SignalR](https://github.com/aspnet/SignalR) service for moving slides along on viewers devices, and live feed of Questions.
- **[Slide](https://github.com/DeckHubApp/Slides)** -
very microservice for storing and serving Slide images in Azure Blob Storage.
- **[Presenter](https://github.com/DeckHubApp/Presenter)** -
microservice for the CLI to interact with, and to render Presenter View.

This Home repo will also contain the Docker Compose and Kubernetes files used to work with the
projects in development mode, and to run them in a Kubernetes cluster in Production.

# Technologies

This project is built upon many others, most of them open source, although with a couple of
Azure-specific Platform-as-a-Service bits. Here are all the ones I can think of right now:

- [ASP.NET Core](https://github.com/aspnet/Home) 2.1, including:
  - [SignalR](https://github.com/aspnet/SignalR) for realtime messaging
  - [Identity](https://github.com/aspnet/Identity) for external authentication
- [Entity Framework Core](https://github.com/aspnet/EntityFramework), plus
  - [Npgsql](https://github.com/npgsql/Npgsql.EntityFrameworkCore.PostgreSQL)
  provider for EF Core
- [.NET CoreRT](https://github.com/dotnet/corert) for building native executables of the CLI tool
- [Markdig](https://github.com/lunet-io/markdig) for the slide rendering
- [SharpYAML](https://github.com/xoofx/SharpYaml) for parsing YAML
- [App Metrics](https://app-metrics.io) for production metrics
- [PostgreSQL](https://www.postgresql.org/) for most data storage
- [Redis](https://redis.io/) for caching and pub/sub messaging
- [MessagePack for C#](https://github.com/neuecc/MessagePack-CSharp) for small, fast messages
- [Azure Service Bus](https://azure.microsoft.com/en-gb/services/service-bus/)
  for message queues
- [Azure Blob Storage](https://azure.microsoft.com/en-gb/services/storage/blobs/)
  for storing slide images
- [Docker](https://www.docker.com/) for building images and running containers, including
  - [Docker Compose](https://docs.docker.com/compose/) for local orchestration
- [Kubernetes](https://kubernetes.io/) for production orchestration

You'll also see references to a couple of my own `dotnet` CLI tools that I think are nifty:

- [dotnet-unpkg](https://github.com/RendleLabs/dotnet-unpkg) for quick-and-dirty installation
  of front-end JavaScript and CSS packages from [unpkg.com](https://unpkg.com)
- [dotnet-embed](https://github.com/RendleLabs/Embedder) for even-quicker-and-dirtier embedding
  of UTF8 text in the CLI tool 
