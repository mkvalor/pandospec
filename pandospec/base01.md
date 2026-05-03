#Project Specification
Here we define a DSL named `Pandospec` (no relation to Pandoc), for files saved with the ".pc" extension, which specifies code structures and logic implemented in the mentioned computer programming language (defaults to the rust programming language if this was not overridden). Any text blob in each element may be imprecise and you are free to map these loose definitions to code as you see fit with the caveat that if you are truly unsure of how to proceed, you should stop implementation and ask me for clarificaion before proceeding (referencing the portion of Pandospec specification that is unclear). Elements of Pandospec may be indented to indicate a hierarchical relation to elements above.  There is no top-level element, so peer elements at the top level (with no indentation may still belong to a single compilation unit; you may decide how many code files to create in order to separate concerns and maintain high cohesioin with low coupling.

bi:Text [basic idea of the system]
  d:Title:Detail Text [describes a detail with a title that may be referred to in chat conversation or documentation]

t:technology 1, technology 2, etc [the preferred mix of programming languages, runtimes, services, and frameworks for implementation. you may choose among these for various concerns related to implementing the specified behavior, generating dynamic code files [if any], building the program, installing the program, spinning up runtime infrastructure, etc. choose the rust computer language with the cargo build chain mixed with make if this element is missng or does not list at least one computer language]

o: [operating environment spec. when an OS is specified, assume a release version within the past two years. If this element is omitted, assume the example values listed in the following example, o:Linux AMD64, CORES:16+ L1D:48K RAM:64GB NW:1GBASE-T]

s:Name [structure]
  ea:Name:Type[first element of the structure, its name, its type; one or many]
  eb:Name:Type[second element, etc]

i:Name:Idea [implementation method for the named struct and text that defines what it should do]

f:Name:Idea [free function definition with a name]
  fp:Type:Name [func param with a required type (may be 'var' for you to choose the type or if the computer language has no types) and an optional name (you choose the name if the name is omitted)]

c:Expression [conditional scope that evaluates an expression; impl may be more parsimonious with variable names than terms used in this definition]
  oa:Evaluation:Action[first outcome: the action to take if the conditional expression matches the value or range of values specified by Evaluation]
  ob:Evaluation:Action[second outcome, etc]
  fo:Evaluation:Action[optional final outcome; action to take if no previous outcomes covered the value of the Expression]

bs:Text [brainstorm concept related to implementing this solution which requires more freedom by you to "flesh out" and fill in the details. you should design this first, producing a new design document markdown file in the current working directory (with a filename in snake case that begins with "bs" and includes a few keywords of the brainstorm idea). then read the new design document afresh before proceeding to implement the concept in code.]

ipc:Text [indicates the binary created by your code will participatin in IPC with other components running as separate processes on the same computer with multiple CPU cores. prefer standard IPC facilities available on Linux backed by bespoke ring buffers to more abstacted options such as GRPC or zeromq, unless otherwise specified]

wsc:Endpoint, Params, Headers, and Auth [call a web service with the optional parameters and headers, and implement the optional auth scheme requested]

wse:Endpoint, Params, Headers, and Auth [call a web service with the optional parameters and headers, and implement the optional auth scheme requested]
