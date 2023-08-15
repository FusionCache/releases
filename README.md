<br/>
<br/>

> **Warning**
> 
> Fusion is pre-release/alpha.

<br/>

FusionCache is a cache for storing, searching and retrieving JSON data. There are two modes:


**KeyValue**

- Data is handled as key values, similar to Redis or Memcached
- Queries and responses are use a WebSocket interface

<br/>

**Objects**

- Data is handled as JSON objects and relationships between objects are tracked
- Queries and responses are handled by REST and WebSocket interfaces, with a dedicated WebSocket interface for bulk data

<br/>

# Install
Fusion is available as a Debian package. There isn't a binary for Windows, but there will be a Docker image soon.

See [install](https://fusioncache.github.io/docs/install/install) docs for more information.

<br/>

# Recent Updates

<br/>

## v0.1.8
14th August 2023
- KV Mode: 
  - Small update for performance tweak, not using all cores


<br/>

## v0.1.7
8th August 2023
- KV Mode: 
  - New query `SETQ` (Set Quiet) which is the same as `SET` but only sends a response on an error
  - New query `ADDQ` (Add Quiet) which is the same as `ADD` but only sends a response on an error

<br/>

## v0.1.6
7th August 2023
- KV Mode: 
  - Values can be arrays or objects
  - New query `RNM_KEY` which renames a key

<br/>

## v0.1.5
5th August 2023
- New "KV Mode", manage data as key-values similar to Redis and memcached
- Changed config file structure (defaults to KV mode)

<br/>

## v0.1.4
24th July 2023
- Configure with JSON config file rather than command line parameters
- Removed all command line parameters except for `--config`
- Default config file provided
- Minimum Bulk read size changed to 8MB
- Maximum WS Normal read size changed to 8MB


<br/>
<br/>

# Older Updates


|Version|Date|
|:---|:---|
| 0.1.3 |13th July 2023|
| 0.1.2 |10th July 2023|
| 0.1.1 |5th July 2023|


<br/>
<br/>


---
<br/>
<br/>

![Microsoft Startup](https://www.fusioncache.io/wp-content/uploads/go-x/u/900e42d9-1db8-4c24-9b96-e35207a55ab3/l2,t0,w781,h336/image-560x241.png)
