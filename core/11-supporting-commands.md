Supporting Commands
=======================

In order to perform useful computation the following supporting commands may be available.

## WAIT

**Parameters**

```
WAIT INPUT_INT
```

**Side-effects**

Yields control to another script. The current script is not resumed for at least the specified number of milliseconds.

This command is useful due to the cooperative multitasking nature of the execution environment.

## GOTO

**Parameters**

```
GOTO LABEL
```

**Side-effects**

Performs a jump to the specified location.

## GOSUB

**Parameters**

```
GOSUB LABEL
```

**Side-effects**

Calls the subroutine in the specified location.

## RETURN

**Parameters**

```
RETURN
```

**Side-effects**

Returns from the last called subroutine.

The behaviour is undefined if there is no active subroutine.

## RETURN_TRUE

**Parameters**

```
RETURN_TRUE
```

**Side-effects**

Returns true (as in any command updating the compare flag to true).

## RETURN_FALSE

**Parameters**

```
RETURN_FALSE
```

**Side-effects**

Returns false (as in any command updating the compare flag to false).

## SCRIPT_NAME

**Parameters**

```
SCRIPT_NAME TEXT_LABEL
```

**Side-effects**

Associates a name to the executing script.

**Constraints**

The translation environment must enforce the following constraints.

The name of a script must be unique across the multi-file.

The behaviour of the translation is unspecified if the name is given by a text label variable.

## TERMINATE_THIS_SCRIPT

**Parameters**

```
TERMINATE_THIS_SCRIPT
```

**Side-effects**

Terminates the executing script.

## START_NEW_SCRIPT

**Parameters**

```
START_NEW_SCRIPT LABEL INPUT_OPT...
```

**Side-effects**

Creates a script and sets its program counter to the specified label location.

The first few local variables at the scope of the target label are assigned the values of the optional input arguments. That is, the first declared local variable is set to the first optional argument, the second variable to the second optional argument, and so on.

**Constraints**

The translation environment must enforce the following constraints.

The specified label location must be within a scope.

The type of a local variable and its respective input argument must match. For instance, if an input argument is an integer literal or variable of integer type, its corresponding local variable in the target scope must be of integer type.

If there are not enough local variables in the target scope to accomodate the input arguments the program is ill-formed.

If an input argument is a variable, the value assignment to the variable in the target scope shall obey the same constraints as specified in the SET alternator.
