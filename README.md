```haskell
newtype TestSudoku = TS Sudoku

instance Arbitrary TestSudoku where
    arbitrary = elements $ map TS sudokus

sudokus :: [Sudoku]
sudokus = easySudokus ++ mediumSudokus ++ hardSudokus ++ evilSudokus
```
