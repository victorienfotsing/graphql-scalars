# usage AplloClient
## use [apollo-link-scalars](https://github.com/eturino/apollo-link-scalars)

```typescript
import { withScalars } from "apollo-link-scalars";
import { GraphQLDate, GraphQLDateTime, GraphQLTime } from "graphql-scalars";
import { ApolloLink, HttpLink } from "@apollo/client/core";
import { schema } from "./my-schema";

const link = ApolloLink.from([
  withScalars({ schema }),
  new HttpLink({ uri: "http://example.org/graphql" })
]);

export const typesMap = {
  Date: GraphQLDate,
  Time: GraphQLTime,
  DateTime: GraphQLDateTime,
  // ...
};


const link2 = ApolloLink.from([
  withScalars({ schema, typesMap }),
  new HttpLink({ uri: "http://example.org/graphql" })
]);
```
