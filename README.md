
Instructions from https://docs.github.com/en/graphql/guides/using-the-explorer.

Install GraphQL Client Altair

```
snap install altair
```

```graphql
query {
    rateLimit {
        cost
        remaining
        resetAt
    }
    search(query: "is:public archived:false created:>2017-12-31", type: REPOSITORY, first: 100, after: null){
        repositoryCount
        pageInfo {
            endCursor
            hasNextPage
        }
        nodes {
            ... on Repository {
                nameWithOwner
                object(expression: "HEAD:CITATION.cff") {
                    ... on Blob {
                        text
                    }
                }
            }
        }
    }
}
```
