# bitplane-gateway

Reaches hosts and routes clients to each host's session daemon by host id.

## Language

**Host**:
A bitplane host, used exactly as bitplane defines it: a place planes live (your machine, a server, a container).
_Avoid_: Realm, machine, node

**Gateway**:
One running `bpg-server`, reached at a stable URL; a client may use several, such as one on your machine and one on a remote server.
_Avoid_: Server (on its own), proxy, router

**Local gateway**:
A gateway on the client's own machine.
_Avoid_: Embedded gateway

**Remote gateway**:
A gateway on another machine, which its user runs and configures.
_Avoid_: Hosted gateway, cloud gateway

**Host list**:
The hosts one gateway can reach, as written in its config.
_Avoid_: Registry, host registry, inventory

**Host entry**:
One host in a host list: its host id and how to reach it.
_Avoid_: Host record, host config

**Host id**:
The name a gateway knows a host by; unique within that gateway's host list, so the same host may carry different ids on different gateways.
_Avoid_: Host name, alias

**Local host**:
The host a gateway runs on, always present under the reserved id `local` and never listed in its host list.
_Avoid_: Localhost, self

**Gateway connection**:
A client's connection to the gateway itself, used to learn the gateway's identity and its host list; it never reaches a daemon.
_Avoid_: Control connection, admin connection

**Host connection**:
A client's connection to one host's session daemon through a gateway; the gateway passes it through unchanged.
_Avoid_: Tunnel, channel, session (a session is a terminal)
