Given `/index.html`

```
<!DOCTYPE html>
<html lang="en">
  <body>
    <h1>Hello world</h1>
  </body>
</html>
```

and `/css/styles.css`

```
html,
body,
main {
  margin: 0;
  min-height: 100%;
}
```

CSS is parsed as:

```
{
  "url": "/css/styles.css",
  "type": "text/css",
  "size": 238,
  "selectors": [
    {
      "token": "html",
      "type: "element"
    },
    {
      "token": "body",
      "type: "element"
    },
    {
      "token": "main"
      "type: "element"
    }
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

HTML is parsed as:

```
{
  "url": "/index.html",
  "type": "text/html",
  "encoding": "UTF-8",
  "doctype": "html",
  "size": 103,
  "tree": [
    "node": "html",
    "attributes": [
      {
        "name": "lang",
        "value": "en"
      }
    ]
    "children": [
      {
        "node": "body",
        "children": [
          {
            "node": "h1",
            "children": [
              "text": "Hello world"
            ]
          }
        ]
      }
    ]
  ]
}
```

Matches:

`<html>` found on line 2, column 1
`<body>` found on line 3, column 3
`<main>` not found

Output:

```
CSS: Unused selector. `main` not found in 1 HTML file.
```
