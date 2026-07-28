<!-- loio34d07897ac764ff998b0a0024b2d7087 -->

# responseHeaders

You can add headers that the application router returns to the client in its responses.

You can add response headers to your application, for example, to comply with security standards.

The `responseHeaders` property is an array of objects, each object having the following properties:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

name

</td>
<td valign="top">

string

</td>
<td valign="top">

response header name

</td>
</tr>
<tr>
<td valign="top">

value

</td>
<td valign="top">

string

</td>
<td valign="top">

response header value

</td>
</tr>
</table>

```
{ "responseHeaders" : [
    {"name": "header1", "value": "value1"},
    {"name": "header2", "value": "value2"}
  ]
}
```

Example:

> ### Sample Code:  
> ```
> { "responseHeaders" : [
>     {"name": "Content-Security-Policy", "value": "default-src 'self'"}
>   ]
> }
> ```

