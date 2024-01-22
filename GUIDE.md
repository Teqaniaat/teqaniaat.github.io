# Writing guide
## YAML Fields
- `title`
- `description`
- `lang` - Either `en` or `ar`
- `layout` - HTML Layout used
- `usemathjax` - `true` if you want to process math notations between 2 `$` signs

Things probably should be added:
- `tags`
- `authors`

Use double quotation `""` in case of string

## Imporing HTML elements
You can include HTML files in `_includes` folder
```
{% include file_name.html %}
```

## Markdown
You can use [Github Flavored Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

## If statements
```
{% if ... %}

{% endif %}
```