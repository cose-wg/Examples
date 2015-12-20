# Examples

This project contains a number of examples and test cases for the IETF COSE WG specification.


The file Example.cddl contains a schema for how the example files are formatted.  

As time and the spec progresses, it is expected that we will start looking at adding examples that fail as well as successful examples.  While every attempt will be made to keep the examples in sync with the specifications, they may trail the current version at times.

# Random number generation

The examples can potentially contain a random number generation stream.  This field contains a re-playable random number generator sequence that is used by the program which generates the examples.  The order in which calls are made to the random number generator should be documented int he description field when this present in the file.
