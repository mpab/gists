# Installation

## opam installation

```console
> curl -sL https://raw.githubusercontent.com/ocaml/opam/master/shell/install.sh > install.sh
> sudo ./install.sh
> opam init --disable-sandboxing --compiler=4.08.1 --yes
```

## scilla installation - navigate to scilla folder

```console
> opam install ./scilla.opam --deps-only --with-test
> opam switch create ./ --deps-only --with-test --yes ocaml-base-compiler.4.08.1
```

fails

```console
> make clean;make
```

fails

ensure default line endings are enabled
install dependencies
make test - installs dune and headers

```console
> git config --global core.autocrlf false
> opam depext
> make test
> opam switch create ./ --deps-only --with-test --yes ocaml-base-compiler.4.08.1
> ln -s ~/path/to/scilla/_opam _opam
> opam install ./scilla.opam
```
