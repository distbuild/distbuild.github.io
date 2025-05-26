# Remote Execution API



## Overview

distbuild is compatible with remote caching and remote execution servers that comply with the [Remote Execution API](https://github.com/bazelbuild/remote-apis) standard ("REAPI"). The REAPI protocol is supported by several different server and client projects including Bazel.

REAPI servers implement several related but distinct services:

- A "content-addressable storage" service that stores data keyed by the hash of that data (also known as a "CAS").

- An "action cache service"  that maps process executions to their results
- An "execution service" that executes processes by using the content-addressable storage service to obtain the inputs and store the outputs from running  those processes.

Remote cache servers implement the CAS and action cache services. Remote execution servers implement all three services.

The REAPI model contains the notion of an "instance." An "instance" is a distinct deployment of a CAS and/or execution service that is given a specific name. All REAPI operations send an instance name to the server, thus a single network endpoint can conceivably support multiple REAPI deployments.



## Test

The [remote-apis-testing project](https://gitlab.com/remote-apis-testing/remote-apis-testing) maintains a compatibility test suite of the various server and client implementations of REAPI.



## Reference

- https://www.pantsbuild.org/docs/remote-caching-execution
