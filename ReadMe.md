### Recursive Quantum Programming
---
This repository presents the implementation of recursive quantum programming in Maude, providing a framework for specifying quantum programs with the syntax of recursive quantum programs and verifying their correctness through reachability analysis with the search command in Maude.

## Dependencies
- Maude is a programming/specification language based on rewriting logic. How to download and install Maude can be found [here](http://maude.cs.illinois.edu/w/index.php/The_Maude_System).
- An algebraic specification for quantum computation ([|AS4QC>](https://github.com/canhminhdo/ket-as4qc)) as a submodule in this repository.

## How to install
- Clone the source code to your computer and go to the source code directory.
```console
git clone --recurse-submodules https://github.com/canhminhdo/qrp.git && cd qrp
```

- Feed a Maude file that is the formal specification of quantum programs in the framework being verified into Maude.

For example, we can type the following command in CLI in order to conduct reachability analysis for quantum network coding specified in the `nwcoding.maude` file:

```console
maude nwcoding.maude
search in NWCODING : < prog, push(empCS, venv), empPEnv, qs > =>! < S:Prog, CS:CallStack, PE:PEnv, V:Vect > such that S:Prog == emp /\ (V:Vect).P(v('q1), v('q6), venv, EPR) /\ (V:Vect).P(v('q2), v('q5), venv, EPR) .
```

- For testing, go to the `test` folder and run the `./tester` file in CLI.

## Case Studies
We successfully verify the correctness of some quantum recursive programs with reachability analysis:
- Quantum Network Coding
- ...

## Publication
TBA
