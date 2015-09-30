Localization Storage Format Specification
=========================================

LSF is standard for localization storage.

It consist of `localized string specification` or `.lsspec` file for defining which localized strings are defined in a project. And a `localized string` or `.ls` files for storing localized strings.

Example of a `.lsspec` file:

```
@languages {
	'en-US': 'localizations/en-US';
	'zh-CN': 'localizations/zh-CN';
	'jp-JA': 'localizations/en-US';
}

@strings {
	'Some localized string1': {
		description: 'A string in label1';
		added: '2014-12-01 10:10:24 UTC';
	}
	
	'Some localized string': {
		description: 'A string in label1';
		added: '2014-12-01 10:10:24 UTC';
	}
}
```

Example of a `.ls` file in this case `en-US.ls`:

```
@strings {
	'Some localized string' {
		value: 'I got {likes, plural, one{# like} other{# likes}}';
		parameters: likes;
	}
	
	<en-US>'Some localized string2'; # Symbols
}
```