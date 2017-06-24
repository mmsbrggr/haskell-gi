```haskell
spec :: Spec
spec = do
    describe "solveSudoku" $ do
        it "should return something" $ property $
            \(TS s) -> isJust $ solveSudoku s

        it "should not contain blank values" $ property $
            \(TS s) -> let solutionStrings = map toString (fromJust $ solveSudoku s)
                       in and $ map (all (/= blankval)) solutionStrings
```
