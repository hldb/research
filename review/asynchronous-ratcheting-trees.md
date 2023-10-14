Title | On Ends-to-Ends Encryption: Asynchronous Group Messaging with Strong Security Guarantees |
---|---|
Link | https://eprint.iacr.org/2017/666 |
DOI | N/A |
Categories | Access-Control |

Summary

## Contributions:

1. Asynchronous Ratcheting Trees (ART), fully-asynchronous tree-based group key exchange protocol that offers modern strong security properties, forward secrecy and post compromise secrecy.
Derives a group key for a set of agents without any pair needing to be online at the same time.
j
2. Game-based computational security model and game-hopping computational proof of the unauthenticated core of our ART protocol, with an explicit reduction to the PRF-ODH problem.

3. Implementation in Java: https://github.com/facebookresearch/asynchronousratchetingtree

## Notes:

- Could be a complete solution for access control by protecting read and write access in a scalable, dynamic, and asynchronous way.
- Forward secrecy property complicates eventual consistency guarantees.
- Hard to handle concurrent edits to the tree without a server. Requires a convergent data type to be built. Might be good to instead investigate [DCGKA](./dcgka.md)

## Solutions: 

- remove forward secrecy and this becomes much easier to use with replication via ipld pinners as history should be totally readable to new agents, a good thing in this situation but hard to change.
- have a weaker consistency model for replication via ipld pinners. complete replication of anything previous to read access being granted would need to be delivered by other peers with complete read access.
- used to share a new symmetric key after a access control change. when read access is granted to a new user they get all previous symmetric keys sent to them. when read access is revoked they are removed from the ART and a new symmetric key is shared.

## Abilities:

- Group Key Exchange / Private Group Messaging with Foward Secrecy and Post-comprimise Security properties
- Fully-asynchronous and Dynamic Membership
