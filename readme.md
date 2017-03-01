# Soy Cheat Sheet

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
	{param name: 'Ray' /}
{/call}
```

```
{call .hello}
	{param name: $name /}
	{param lastName: $lastName}
{/call}
```

```
{call .hello data="all" /}
```

## Variables

```
{let $name: 'Ray' /}
```

```
{let $name}
	Ray
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
{elseif $name == 'Female'}
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

```
{augmentMap(map1, map2)}
{ceiling(number)}
{floor(number)}
{isNonnull(value)}
{keys(map)}
{length(list)}
{max(number, number)}
{min(number, number)}
{randomInt(number)}
{round(number)}
{strContains(string, subString)}
```