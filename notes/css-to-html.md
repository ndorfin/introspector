Given:

```
html,
body,
main {
  margin: 0;
  min-height: 100%;
}

```

Becomes:

```
{
  "selectors": [
    "html",
    "body",
    "main"
  ],
  "declarations: [
    {
      "property": "margin",
      "value": 0
    },
    {
      "property": "min-height",
      "value": "100%"
    }
  ]
}
```

Matches:

```
<html lang="en">...</html>
<body>...</body>
```

Doesn't match:

```
<main> element not found
```
