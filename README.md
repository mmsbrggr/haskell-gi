```haskell
buildSudokuUI :: IO SudokuUI
buildSudokuUI = do
    uiFile            <- T.pack <$> getDataFileName "gui/hsudoku.ui"
    (window, builder) <- buildMainWindow "mainWindow" uiFile
    menu              <- builderGetTyped builder "menu" Widget
    gameButtons       <- builderGetsTyped builder gameButtonNames Button
    cells             <- builderGetsTyped builder cellNames Button
    popover           <- builderGetTyped builder "inputPopover" Popover
    numberButtons     <- builderGetsTyped builder numberNames Button
    inputClear        <- builderGetTyped builder "inputClear" Button
    inputSolve        <- builderGetTyped builder "inputSolve" Button
    solveButton       <- builderGetTyped builder "solveButton" Button
    checkButton       <- builderGetTyped builder "checkButton" Button
    menuButton        <- builderGetTyped builder "menuButton" Button
    pure $ SudokuUI window menu gameButtons cells popover
                    numberButtons inputClear inputSolve solveButton
                    checkButton menuButton
```
