# Basic Graphql Server With Dune

## Purpose

Purpose is to show how to run and existing dune built project.

## Setup

1. `mkdir project-name` and `cd project-name`.
2. Create local opam switch. Run `opam switch create . ocaml-base-compiler.4.07.0` which will install all the deps listed in the `server.opam` file.
3. If you were running this from scratch, you would have `opam install digestif.c lwt lwt.unix graphql-lwt graphql-cohttp cohttp-lwt cohttp-lwt-unix` to install the libraries you wanted to use in this project.
4. You would list those libraries in your [`dune`](./dune) file. See nice [medium article](https://medium.com/@bobbypriambodo/starting-an-ocaml-app-project-using-dune-d4f74e291de8) with breakdown. Older but still good.


```dune
(executable
  (name server)
  (libraries digestif.c lwt lwt.unix graphql-lwt graphql-cohttp cohttp-lwt cohttp-lwt-unix))

(alias
  (name DEFAULT)
  (deps server.exe))
```

5. Build the project with `dune build server.exe` where server is the name you gave to the executable.
6. Run with ``dune exec server.exe`.

