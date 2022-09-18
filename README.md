# Atlan SQL Client

### Introduction about the project

It's an SQL client that fetch the data as per the query, and allow user to sort and filter the results.

### Major Plugins/Libraries

Vue3 & Vuetify

#### Performance

The page render takes around 1.25 secs. I measured it using Lighthouse in the chrome dev tools.

As part of performance improvements I did optimise the components to not cause a lot of rerenders. More could be done on reducing the bundle size.
