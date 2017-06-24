```haskell
solve :: Board -> [Board]
solve = map (map $ map head) . search . prune . choices
```
