<br/>

> **Warning**
> 
> Fusion is pre-release/alpha. There may be bugs and changes to query structure.

<br/>

See [install](https://fusioncache.github.io/docs/install/install) docs.

<br/>

# Recent Versions

<br/>

## v0.1.2
10th July 2023
- New query: `OIDS` which returns all OIDS for a class
- Network I/O: reduce threads assigned to network I/O
- Query Engine: only queue threads if necessary

<br/>

## v0.1.1
5th July 2023
- The first alpha version, supporting the fundamental queries (`STORE`, `GET`, `FIND`, `DELETE`, etc)
- x86 64bit only
  - ARM version to follow
- Debian package
  - Docker image to follow
- Some performance testing but not exhaustive
- Limited to 64 threads (it will run on systems with more but will act as if only having 64)
  - This isn't a technical limitation, it'll be increased after more testing


<br/>

# Partnership
In July 2023 FusionCache was accepted onto the Microsoft For Startups programming. This gives access to Azure services and will open opportunities as the software develops.

![Microsoft Startup](https://www.fusioncache.io/wp-content/uploads/go-x/u/900e42d9-1db8-4c24-9b96-e35207a55ab3/l2,t0,w781,h336/image-560x241.png)
