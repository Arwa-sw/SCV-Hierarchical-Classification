# Variable Shadowing

## Deffrent Names:
( Variable Shadowing , Built-in symbol shadowing)

## Describe: 
Shadowing means an element hiding another element with the same name. It occurs when the developer uses the same name of an element (local 
variable, function, or event) in different scopes (multiple definitions for the same name), which would result in two separate versions of the 
element, hence the incorrect reference.

## Its danger:

## Solution:
 Review storage variable layouts for your contract systems carefully and 
 remove any ambiguities. Always check for compiler warnings as they can flag the issue within a single contract.

## Tools can detect:
  Slither.
