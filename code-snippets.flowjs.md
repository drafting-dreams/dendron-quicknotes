---
id: reuQPhxjYWO0jP2LQGqKE
title: Flowjs
desc: ''
updated: 1639899545522
created: 1639898860757
---

# How to write Injection HOC in flowjs?

```flow
function withContext<T: $Exact<ContextFromState>>(
  Component: React.ComponentType<T>,
): React.ComponentType<$Diff<T, $Exact<ContextFromState>>> {
  return function ComponentWithContext(
    props: $Diff<T, $Exact<ContextFromState>>,
  ) {
    return (
      <ProductBriefingContextFromState.Consumer>
        {(context) => <Component {...props} {...context} />}
      </ProductBriefingContextFromState.Consumer>
    )
  }
}
```

# Enum of flowjs

https://stackoverflow.com/questions/39154870/how-to-use-define-enums-with-flow-type-checking#answer-49105296

```flow
export const Status = Object.freeze({
  PENDING: 'pending',
  SUCCESS: 'success',
  FAILED: 'failed',
})
```

And the type of `Status` is

```flow
$Values<typeof Status>
```
