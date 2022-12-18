# Opalescent
A peer-to-peer database protocol

## Summary

Opalescent can be used to build [local-first](https://www.inkandswitch.com/local-first/), decentralized applications.
It is best suited for social/collaborative applications that do not require consensus.

Each peer has their own copy of the database called a replica.
The peer's local replica is used as the source of truth.
Updated remote replicas are merge with the local replica to see the new state.

In this way, the applications are edge-computed by the participating peers.
Applications designed this way give users more control with potential to make large scale database breaches a thing of the past.

## Encryption?

There is no encryption built into the protocol yet.

## Access Control

Currently only write access can be controlled and is not able to be updated for now.
Access is controlled and enforced by correct peers on their own replicas.

## Papers

The core of the database is the replica which is a *Merkle-CRDT*. This type of [CRDT](https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type) allows for BEC, byzantine eventual consistency, which is a strong property on top of [SEC](https://en.wikipedia.org/wiki/Eventual_consistency#Strong_eventual_consistency) that ensures faulty replicas cannot permanently corrupt the state of correct replicas.

These are two papers the fundamentals of `opalsnt` are built on:

1. [Merkle-CRDTs: Merkle-DAGs meet CRDTs](https://research.protocol.ai/publications/merkle-crdts-merkle-dags-meet-crdts/)
2. [Byzantine Eventual Consistency and the Fundamental Limits of Peer-to-Peer Databases](https://github.com/ept/byzantine-eventual)

## Specification

The protocol specification can be found in [`opalsnt/specs`](https://github.com/opalsnt/specs).

## Implementations

| Name | Language |
| --- | --- |
| [welo](https://github.com/opalsnt/welo) | typescript |
