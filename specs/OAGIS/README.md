# Open AGI Specifications (OAGIS)

---

## Introduction to AGIs
AGIs (Application GeoDiVMac Interfaces) are the link between a GeoDiVMac and any other software (including anothere GeoDiVMac). These AGIs are the bases for all access to web3. AGIs are programs writen in whatever language the GeoDiVMac supports for scripting and acts as an interface for other programs to easily access the GeoDiVMac.

## Introduction to OAGIS
OAGIS is a language-agnostic specification for building AGIs with CAT or GRAPHQL-like interfaces. 

## Protocol

When a node connects to a GDVM and has peers, it can send a `[agi_name, [args], [g-args]]` message to it's peers via TCP. This will access an AGI named agi_name.

**Command Details**
- program_name: The name of the designated program it would like to access on the GDVM.
- args: extra arguments for the program.
- g-args: arguments for the GeoDiVMac implementation. These arguments are not neccessarily the same across all GeoDiVMacs and a absolutely optional.

## AGI Protocols
AGIs can be implemented in two major protocols. CAT and GRAPHQL.

## CAT AGI Specifications
CAT stands for Customizable Access Tags. CAT is an xml-like syntax for fetching data from backends hosted on a GeoDiVMac. CAT documents follow the following structure where anything in all CAPS is supposed to be replaced with a value.

```
<cat>
    <query-title>TITLE</query-title>
    <method>METHOD</method>
    <metadata>
        <KEY>VALUE</KEY>
    </metadata>
    <payload>
        <KEY>VALUE</KEY>
    </payload>
</cat>
```

Where:

- query-title is the specific query being called.
- method is one of the CAT methods CREATE, READ, UPDATE, DELETE.
- metadata contains metadata about the request like authentication formed in key-value pairs.
- payload contains any payload for the request like IDs in key-value format.

Once a cat document is made, it can be sent via the protocol above in the as the first elemtent in the `[args]` list.

## GRAPGHQL for AGIs
To use graphql, take the data that is sent over the url-encoded key-value pairs and just use the same key-value pairs as JSON as the first elemtent in the [args] list.

---
## Any terms which are not commonly used can be found in Terms.md at the root of the direcory
