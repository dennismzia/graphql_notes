<!-- more time to config #sighs -->

generate documentation with spectaql if introspection enabled.

introspection query
https://github.com/dolevf/Black-Hat-GraphQL/blob/master/queries/introspection_query.txt

graphql voyager
http://lab.blackhatgraphql.com:9000/

-   schema getting directive description

```gql

query GetDirectives {
    __schema {
        directives {
            name
            description
            locations
        }
    }
}

```

-   spoofing operationNames to bypass filters

```gql

mutation SpoofedOperationName {
    createPaste(
        title: "Black Hat GraphQL"
        content: "I just spoofed the operation name."
    ) {
        paste {
            content
            title
        }
    }
}

```

-   Returns mutations that exist in a schema

```gql

query {
    __schema {
        mutationType {
            fields {
                name
            }
        }
    }
}

```

-   extension for above command to know what types and args a mutation takes

```gql

query {
    __type(name: "YourMutationName") {
        name
        kind
        description
        inputFields {
            name
            type {
                name
                kind
            }
        }
    }
}

```

-   inrospection query to extract query field names

    ```gql

    query {
        __schema {
            queryType {
                fields {
                    name
                }
            }
        }
    }

    ```




-   extension of above command but returns the type and names of the fields

```gql

query {
    __schema {
        queryType {
            fields {
                name
                type {
                    name
                    kind
                    ofType {
                        name
                        kind
                        fields {
                            name
                        }
                    }
                }
            }
        }
    }
}

```

-   An introspection query for discovering fields within an object of interest

```gql

query {
    __type(name: "PasteObject") {
        name
        kind
        fields {
            name
            type {
                name
                kind
            }
        }
    }
}

```
-  just like above but returns more infromation of a grpahql object or input object or anything really

```
{
  __type(name: "BrandPermissionsInput") {
    kind
    name
    fields {
      name
      type {
        kind
        name
        ofType {
          kind
          name
        }
      }
    }
    inputFields {
      name
      type {
        kind
        name
        ofType {
          kind
          name
        }
      }
    }
  }
}
```

- introspection query that extends above use this if above returns null
```gql
query {
    __type(name: "PayflowLinkTokenInput") {
        name
        kind
        inputFields {
            name
            type {
                name
                kind
            }
        }
    }
}
```


-   introspection query for schema types

```gql

query {
    __schema {
        types {
            name
        }
    }
}

```

```gql

query {
    __schema {
        subscriptionType {
            fields {
                name
            }
        }
    }
}

```

circular queries

```bash

inql -f /home/kali/introspection_query.json --generate-cycles -o dvga_cycles

```

-To generate a SHA-256 hash of any query, you can use the sha256sum
command, like so:

```bash
echo -n "{query{pastes{owner{id}}}}" | sha256sum
```
