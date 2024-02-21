# miscellaneous notes

-   searching web archive

```html
http://web.archive.org/cdx/search/cdx?url=google.com%2Fapi%2F*&output=text&fl=original&collapse=urlkey&from=
```

-   Uncontrolled resource consumption

Azure shared access signature ie sas token if it doesnt have the appropriate expiration dat e or limit then attack here is to download and big blob (data) like 200GB and download it 10 times that will cause the usage to go up to 2TB.

url would look like
```
https://youraccount.blob.core.windows.net/?restype=container&comp=list&sv=2022-11-02&se=2023-05-24T09:51:36Z&sp=r&sig=<signature>

```