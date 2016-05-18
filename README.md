xHain hack+makespace
====================

## Translation

Translated versions of German pages have a `.en` before the file extension (this
is a convention and not a requirement).

Example:

- German: `support.html`
- English: `support.en.html`

This is only to keep the files together internally. The public-facing pages
(i.e. the ones *generated* by Jekyll) should instead be placed in
language-specific directories (or the root directory `/` for German files).

Example:

- German: `/support.html`
- English: `/en/support.html`

Jekyll doesn't do this automatically, instead you have to manually set the
`permalink` property in the metadata. See `support.en.html` for an example
of what the metadata block of translated pages should look like.

By default, all pages have a link to the translated version at the top right
of the page. If the conventions above are followed, these can be generated
automatically. Otherwise, the **links to translated pages can be overriden or
disabled** using the `translations` metadata property.

Examples:

Consider a page at `/news/2016/01/01/beispiel.html`. Its English version can be
found at `/en/news/2016/01/01/example.html` rather than `/en/…/beispiel.html`.
To link the two:

```yaml
# In _posts/2016-01-01-beispiel.html:
translations:
  en: /en/news/2016/01/01/example.html

# In _posts/2016-01-01-beispiel.en.html:
translations:
  de: /news/2016/01/01/beispiel.html
```

If a page doesn't have a translated version, you can disable the link by
passing `false` instead of the URI, like so:

```yaml
# On a German-language page without an English translation:
translations:
  en: false
```
