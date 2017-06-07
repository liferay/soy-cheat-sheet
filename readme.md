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

```soy
{namespace foo}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#namespace "Namespace")

## Template

```soy
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

```soy
/**
 *
 */
{template .hello}
	{@param name: string}

	Hello {$name}
{/template}
```

###### optional

```soy
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

```soy
{call .hello}
	{param name: 'Jon' /}
{/call}
```

```soy
{call .hello}
	{param name: $name /}
	{param lastName: $lastName /}
{/call}
```

```soy
{call .hello data="all" /}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#call "Call")

## Variables

```soy
{let $name: 'Jon' /}
```

```soy
{let $names: [
	['first': 'Jon', 'last': 'Snow'],
	['first': 'Arya', 'last': 'Stark']
] /}
```

###### kind

```soy
{let $name kind="text"}
	Jon
{/let}
```

```soy
{let $name kind="html"}
	<p>Jon</p>
{/let}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#let "Let")

## Conditionals

###### if

```soy
{if $name}
	Hello {$name}
{/if}
```

###### if and

```soy
{if $name and $lastName}
	Hello {$name} {$lastName}
{/if}
```

###### if not

```soy
{if not $name}
	Hello there
{/if}
```

###### else

```soy
{if $name}
	Hello {$name}
{else}
	Hello there
{/if}
```

###### elseif

```soy
{if $gender == 'Male'}
	Hello Sir
{elseif $gender == 'Female'}
	Hello Madam
{/if}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#if "If / Else / ElseIf")

###### switch

```soy
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

###### elvis

```soy
Hello {$name ?: 'there'}
```

###### ternary

```soy
{$name ? 'Hello {$name}' : 'Hello there'}
```

> [See Docs](https://developers.google.com/closure/templates/docs/concepts#operators "Operators")

## Loops

###### foreach

```soy
{foreach $name in $names}
	Hello {$name}
{/foreach}
```

###### ifempty

```soy
{foreach $name in $names}
	Hello {$name}
{ifempty}
	Hello there
{/foreach}
```

> [See Docs](https://developers.google.com/closure/templates/docs/commands#foreach "Foreach / Ifempty")

## Special Characters

###### literal

```soy
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

```soy
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

```soy
{isNonnull(value)}
```

###### string

```soy
{strContains(string, subString)}
```

###### number

```soy
{ceiling(number)}
{floor(number)}
{max(number, number)}
{min(number, number)}
{randomInt(number)}
{round(number)}
```

###### foreach

```soy
{index($var)}
{isFirst($var)}
{isLast($var)}
```

###### list

```soy
{length(list)}
```

###### map

```soy
{augmentMap(map1, map2)}
{keys(map)}
```

> [See Docs](https://developers.google.com/closure/templates/docs/functions "Functions")
