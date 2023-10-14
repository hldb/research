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

## Constraints:

- forward secrecy may prevent new peers the ability to read history when combined with some replica structures. either 1) FS needs to be removed by generating seperate AES keys for encrypting db operations and sharing all previous keys with new readers or 2) readers upload a [compacted] delta encrypted with the new keys.

## Abilities:

- Group Key Exchange / Private Group Messaging with Foward Secrecy and Post-comprimise Security properties
- Fully-asynchronous and Dynamic Membership
