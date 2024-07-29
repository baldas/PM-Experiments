
# This is based on TinySTM's intset source code.

To compile, use `make`

Use `-h` to see the options.

To save the relevant information to a file use (redirect the stderr to a file):

`tracegen <options> 2> <file>`

## Format of the output:

The list of the set contents separated by comma

Followed by the operations with the following format:

`<id> - <value>`

where <id> could be:
`0 - insert`
`1 - remove`
`2 - search`
