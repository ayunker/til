# Refetch Query with Apollo GraphQL Client

The Apollo GraphQL client allows you to easily refetch query results, which can
come in super handy if you need to refresh data after some user action on the
page. You can do this with the `refetch` function from `useQuery`:

``` ts
const { data, loading, refetch } = useQuery(QUERY)
```

Then if you want to refetch data after a button click, you can:

``` ts
<button onClick={() => refetch()}>
  Refetch the data!!
</button>
```

If you defined any variables in the initial `useQuery`, refetching will re-use
those variables, but you can override them as well in the call to `refetch`:

```ts
refetch({ param: "new value" });
```

If you need to refetch data after a mutation, you [can do that
too](https://til.hashrocket.com/posts/ssyxhw8kqc-apollo-react-hooks-can-easily-refetch-queries).

[Docs](https://www.apollographql.com/docs/react/data/queries/#refetching)

via: https://til.hashrocket.com/posts/oylccahhkj-refetch-query-with-apollo-graphql-client
