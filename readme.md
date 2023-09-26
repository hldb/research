# hldb/research

> This repo is for written review of existing research with the goal of improving HLDB's protocol design.

## Repo Structure

[/review](./review): review of research papers and which categories they are relevant to.

[/categories](./categories): details of different solutions for each category with their pros/cons.

[/solutions](./solutions): comparisons of complete p2p db solutions using solutions from each category.

## Requirements

The HLDB protocol should be able to fill each of these requirements, so all solutions will keep these in mind.

1. hldb is a [local-first](https://martin.kleppmann.com/papers/local-first.html) database protocol.
2. access-control must support dynamic adds/removes of read or write access.
3. replication must play well with both p2p replication and through simple data hosts.
4. data representation is general-purpose/universal and able to merge nested properties.

> This list may change as the different areas are better understood while researching.


