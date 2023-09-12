<br/>
<br/>

> **Warning**
> 
> Fusion is pre-release/alpha.

<br/>

FusionCache provides a cache for storing and searching data, and a publish subscribe server for distributing data. Data is always handles as JSON.

There are three modes: KeyValue, PublishSubscribe and Objects. The mode is set in the configuration file, rather than supporting different modes during runtime. This is gives more control over CPU and memory resources.

<br/>

## KeyValue

- Data is handled as key values, similar to Redis or Memcached
- Queries and responses are via WebSocket interface

<br/>

## Publish Subscribe

- Fusion acts as a publish subscribe server
- Channels are created, to which publishers send messages, whilst subscribers receive messages
- Messages are exchanged via a WebSockets interface

<br/>

## Objects

- Data is handled as JSON objects and relationships between objects are tracked
- Queries and responses are handled by REST and WebSocket interfaces, with a dedicated WebSocket interface for bulk data

<br/>
<br/>

# Install & Run
Fusion is available as a Debian package. There isn't a binary for Windows, but there will be a Docker image soon.

## Clone
Clone the repo as normal and install with `dpkg` as below

## Download
- Click on the `.deb` file then click the download file icon on the **far right**:

![image](https://github.com/FusionCache/releases/assets/129124415/c7fdba54-5a22-471d-bb85-7406ab2ad666)

## Install
- Install package: `sudo dpkg -i fusioncache_0.1.9_amd64.deb`
- This installs to: `/usr/local/bin/fusioncache`

## Run
- Run the server:  `./fusionserver --config=default.json`
- By default, it starts in KV mode with settings:
   - IP: 127.0.0.1
   - Port: 1987
   - Max read buffer: 64 bytes


See [install](https://fusioncache.github.io/docs/install/install) docs for more information.

<br/>
<br/>

# Configure

These can be changed in the `default.json` config file.

`mode` can be either:  `kv`, `pubsub` or `objects`.

Each of mode require specific settings. Defaults are:

**kv**

```json
{
  "mode":"kv",
  "kv":
  {
    "ws":
    {
      "ip":"127.0.0.1",
      "port":1987,
      "maxRead":64
    }
  }
}
```

**objects**

```json
{
  "mode":"objects",
  "objects":
  {
    "restQuery":
    {
      "enabled":true,
      "ip":"127.0.0.1",
      "port":1981,
      "maxRead":1024
    },
    "wsQuery":
    {
      "enabled":true,
      "ip":"127.0.0.1",
      "port":1982,
      "maxRead":1024
    },
    "bulkStore":
    {
      "enabled":false,
      "ip":"127.0.0.1",
      "port":1983,
      "maxRead":8388608
    }
  }
}
```

**pubsub**
```json
{
  "mode":"pubsub",
  "pubsub":
  {
    "data":
    {
      "ip":"127.0.0.1",
      "port":1990,
      "maxRead":256
    }
  }
}
```


<br/>
<br/>

# Recent Updates

<br/>

## v0.1.9
09 September 2023
- Publish Subscribe 
  - Added lightweight pubsub server
  - Config file can have `pubsub` mode and section to support this
  - See [docs](https://fusioncache.github.io/docs/psapi/)


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
<br/>

# Older Updates


|Version|Date|
|:---|:---|
| 0.1.6 | 7th August 2023|
| 0.1.5 |5th August 2023|
| 0.1.4 |24th July 2023|
| 0.1.3 |13th July 2023|
| 0.1.2 |10th July 2023|
| 0.1.1 |5th July 2023|


<br/>
<br/>


---
<br/>
<br/>

![Microsoft Startup](https://www.fusioncache.io/wp-content/uploads/go-x/u/900e42d9-1db8-4c24-9b96-e35207a55ab3/l2,t0,w781,h336/image-560x241.png)
