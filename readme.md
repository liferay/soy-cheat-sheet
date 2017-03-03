<p align="center">
	<img src="https://cloud.githubusercontent.com/assets/398893/23471606/ccc436a2-fe5e-11e6-954d-ec1449b4a961.png" alt="Logo">
</p>

<h1 align="center">Soy Cheat Sheet</h1>

A collection of cool hidden and not so hidden features, to be used as a quick reference so that you turn coffee into code much faster :)

## Table of Contents

* [Namespace](#namespace)
* [Template](#template)
* [Parameters](#parameters)
* [Parameter Types](#parameter-types)
* [Call](#call)
* [Variables](#variables)
* [Conditionals](#conditionals)
* [Loops](#loops)
* [Special Characters](#special-characters)
* [Functions](#functions)

## Namespace

```
{namespace foo}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#namespace "Namespace")

## Template

```
/**
 *
 */
{template .hello}
	Hello world
{/template}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#template "Template")

## Parameters

###### required

```
/**
 *
 */
{template .hello}
	{@param name: string}

	Hello {$name}
{/template}
```

###### optional

```
/**
 *
 */
{template .hello}
	{@param? name: string}

	Hello {$name}
{/template}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#param "Parameters")

## Parameter Types

###### primitive types

```
string
bool
int
float
number
```

###### other types

```
any
?
null
html
```

###### complex types

```
list<Type>                // List
map<KeyType, ValueType>   // Map
[a:KeyType, b:ValueType]  // Record
Type1|Type2               // Union
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#parameter-type-expressions "Parameter Types")

## Call

```
{call .hello}
	{param name: 'Jon' /}
{/call}
```

```
{call .hello}
	{param name: $name /}
	{param lastName: $lastName /}
{/call}
```

```
{call .hello data="all" /}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#call "Call")

## Variables

```
{let $name: 'Jon' /}
```

```
{let $names: [
	['first': 'Jon', 'last': 'Snow'],
	['first': 'Arya', 'last': 'Stark']
] /}
```

###### kind

```
{let $name kind="text"}
	Jon
{/let}
```

```
{let $name kind="html"}
	<p>Jon</p>
{/let}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#let "Let")

## Conditionals

###### if

```
{if $name}
	Hello {$name}
{/if}
```

###### if and

```
{if $name and $lastName}
	Hello {$name} {$lastName}
{/if}
```

###### if not

```
{if not $name}
	Hello there
{/if}
```

###### else

```
{if $name}
	Hello {$name}
{else}
	Hello there
{/if}
```

###### elseif

```
{if $gender == 'Male'}
	Hello Sir
{elseif $gender == 'Female'}
	Hello Madam
{/if}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#if "If / Else / ElseIf")

###### switch

```
{switch $gender}
  {case 'Male'}
    Hello Sir
  {case 'Female'}
    Hello Madam
  {default}
    Hello Human
{/switch}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#switch "Switch")

###### ternary

```
{isNonnull($name) ? 'Hello {$name}' : 'Hello there'}
```

> [See Docs](https://developers.google.com/closure/templates/docs/concepts#operators "Operators")

###### elvis (null-coalescing)

```
Hello {$name ?: 'there'}
```

> [See Docs](https://developers.google.com/closure/templates/docs/concepts#operators "Operators")

## Loops

###### foreach

```
{foreach $name in $names}
	Hello {$name}
{/foreach}
```

###### ifempty

```
{foreach $name in $names}
	Hello {$name}
{ifempty}
	Hello there
{/foreach}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#foreach "Foreach / Ifempty")

## Special Characters

###### literal

```
{literal}
	<pre>
	function() {
		console.log('Hello');
	}
	</pre>
{/literal}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#literal "Literal")

###### miscellaneous

```
{sp}  // space
{nil} // empty string
{\n}  // newline
{\r}  // carriage return
{\t}  // tab
{lb}  // left brace
{rb}  // right brace
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#specialcharacters "Special Characters")

## Functions

###### any

```
{isNonnull(value)}
```

###### string

```
{strContains(string, subString)}
```

###### number

```
{ceiling(number)}
{floor(number)}
{max(number, number)}
{min(number, number)}
{randomInt(number)}
{round(number)}
```

###### foreach

```
{index($var)}
{isFirst($var)}
{isLast($var)}
```

###### list

```
{length(list)}
```

###### map

```
{augmentMap(map1, map2)}
{keys(map)}
```

> [See Docs](https://developers.google.com/closure/templates/docs/functions "Functions")
