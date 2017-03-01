# Soy Cheat Sheet

[Liferay](https://www.liferay.com/) has been using [Soy templates](https://developers.google.com/closure/templates/) (aka. Google Closure templates) extensively in production.

So we decided to create a collection of cool hidden and not so hidden features, to be used as a quick reference so that you turn coffee into code much faster :)

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
 * @param? lastName 
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
	Hello Sir!
{elseif $name == 'Female'}
	Hello Madam!
{/if}
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
