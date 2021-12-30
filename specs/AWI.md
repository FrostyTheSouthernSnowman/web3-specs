# Specifications for AWIs

---

## AWIs
AWIs (Application Web3 Interfaces) are the link between a GDVM and any other sofware (including anothere GDVM). These AWIs are the bases for all access to web3. AWIs are programs writen in whatever language the GDVM supports for scripting and acts as an interface for other programs to easily access the GDVM. 

## Protocol

When a node connects to a GDVM and has peers, it can send a `{run_program: program_name, p-args: [args], g-args: [args]}` command to it's peers via TCP. 

**Command Details**
- program_name: The name of the designated program it would like to access on the GDVM.
- p-args: extra arguments for the program.
- g-args: arguments for the GDVM implementation. These arguments are not neccessarily the same across all GDVMs.

## AWI Protocol

TODO: add stuff here.

---
## Any terms which are not commonly used can be found in Terms.md at the root of the direcory
