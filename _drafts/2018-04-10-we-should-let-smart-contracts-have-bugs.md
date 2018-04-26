---
title: "We should let smart contracts have bugs"
tags: [blockchain, programming]
image: bitcoin-balance.jpg
featured: "false"
draft: "true"
---
A Typhoon aircraft is several million lines of code. Without the software, it cannot fly. If the software suddenly shuts off, it ceases to be an aircraft. In fact, its wings would fall off within about 2 seconds and the entire plane would be pulverized due to its fundamental aerodynamic instability.

Formal verification is primarily used for hardware verification and chips. Every software project uses formal methods.

"Software is a fashion industry with delusions of grandeur." Prof. Les Hatton

Unambiguous, mathematically designed, formal languages: Haskell, OCAML, Scheme

Formal verification of aircrafts has been done since the 90s, and using type theory to prove properties like no buffer or integer overflow.

Helicopter verification in '95, using things like theorem provers.

Smart cards have been formally verified. Biometric software systems from the NSA have been formally verified.

Formal methods tend to disappear as they become accepted—i.e., they just become part of the toolchain. Examples are compiler optimizations, basic static analysis tools, and stronger type systems.

Security changes everything. Against a malicious and capable attacker, "test it a lot" verification will simply not be good enough.



TYPES OF FORMAL VERIFICATION

Model checking - modeling the state space and describing possible states. Does not scale to large systems.

Deductive verification - using theorem provers or SMT solvers to prove theorems about an algorithm. Requires the user to convey details about the system to the theorem proven and create exhaustive specifications of the system components.

Type systems do this! They establish correctness against fairly limited specifications. Dependently typed languages support deductive verification as a special case.

Hardware formal verification is demanded by the growing complexity of designs. Almost all hardware companies use formal verification, given that errors have dramatic commercial significance and bugs cannot be fixed. Important aspects of hardware design are amenable to automated proof methods, which makes formal verification easier. A few OSes have been formally verified, but no major ones.

Software verification (complete formal proof of correctness) has been around since the 60s, but relatively few major successes.

Checking propositional formulae is NP-complete.

Bancor Attack is an example of something that is extremely difficult to formally verify, because it's extrinsic to the program itself!

https://pron.github.io/posts/correctness-and-complexity

https://www.youtube.com/watch?v=aLWw-uV_qvI
https://www.youtube.com/watch?v=DrDIcirrhWM
https://www.youtube.com/watch?v=rx0NPckEWGI
