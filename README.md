```haskell
spec :: Spec
spec = do
    describe "delete" $ do
        it "should not contain the deleted elements" $ property $
           \xs ys -> delete xs (xs ++ ys) == (ys :: [Int])
```
