<p align="center">
	<img src="https://cloud.githubusercontent.com/assets/398893/23471606/ccc436a2-fe5e-11e6-954d-ec1449b4a961.png" alt="Logo">
</p>

<h1 align="center">Soy Cheat Sheet</h1>

[Liferay](https://www.liferay.com/) has been using [Soy templates](https://developers.google.com/closure/templates/) (aka. Google Closure templates) extensively in production.

So we decided to create a collection of cool hidden and not so hidden features, to be used as a quick reference so that you turn coffee into code much faster :)

## Table of Contents

* [Namespace](#namespace)
* [Template](#template)
* [Parameters](#parameters)
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

## Template

```
/**
 *
 */
{template .hello}
	Hello world
{/template}
```

## Parameters

```
/**
 * @param name
 */
{template .hello}
	Hello {$name}
{/template}
```

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

###### ternary

```
{$name ?: 'Hello {$name}'}
```

```
{$name ? 'Hello {$name}' : 'Hello there'}
```

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
