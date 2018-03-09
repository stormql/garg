
Start with this [fork](https://github.com/rwieruch/react-graphql-github-apollo)...

[Replace this code for better reliability](https://github.com/rwieruch/react-graphql-github-apollo/blob/master/src/index.js#L15)

In the src directory do this...

```
mkdir data
cd data
touch f1.js
```

and then put this line of code in the file...

```
export const key = 'github-auth-token-goes-here'
```

In src/index.js

```
import { key } from "./data/f1.js";
```

and replace the current httpLink code with this...

```
const httpLink = new HttpLink({
  uri: "https://api.github.com/graphql",
  headers: {
    authorization: `bearer ${key}`
  }
});
```
