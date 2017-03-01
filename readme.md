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