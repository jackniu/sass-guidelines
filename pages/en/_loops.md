
# Loops

Because Sass provides complex data structures such as [lists](#lists) and [maps](#maps), it is no surprise that it also gives a way for authors to iterate over those entities.

However, the presence of loops usually implies moderately complex logic that probably does not belong to Sass. Before using a loop, make sure it makes sense and that it actually solves an issue.

## Each

The `@each` loop is definitely the most-used out of the three loops provided by Sass. It provides a clean API to iterate over a list or a map.

{% include snippets/loops/01/index.html %}

When iterating on a map, always use `$key` and `$value` as variable names to enforce consistency.

{% include snippets/loops/02/index.html %}

Also be sure to respect those guidelines to preserve readability:

* Always an empty new line before `@each`;
* Always an empty new line after the closing brace (`}`) unless the next line is a closing brace (`}`).

## For

The `@for` loop might be useful when combined with CSS’ `:nth-*` pseudo-classes. Except for these scenarios, prefer an `@each` loop if you *have to* iterate over something.

{% include snippets/loops/03/index.html %}

Always use `$i` as a variable name to stick to the usual convention and unless you have a really good reason to, never use the `to` keyword: always use `through`. Many developers do not even know Sass offers this variation; using it might lead to confusion.

Also be sure to respect those guidelines to preserve readability:

* Always an empty new line before `@for`;
* Always an empty new line after the closing brace (`}`) unless the next line is a closing brace (`}`).

## While

The `@while` loop has absolutely no use case in a real Sass project, especially since there is no way to break a loop from the inside. **Do not use it**.
