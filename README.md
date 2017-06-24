```haskell
buildMainWindow = liftIO $ do
    builder <- builderNewFromFile "hsudoku.xml"
    window  <- builderGetTyped builder "mainWindow" Window
    on window #destroy mainQuit
    pure (window, builder)

-- Helper function for getting type widgets from the builder
builderGetTyped builder id gtype =
    liftIO $ do
        o <- builderGetObject builder id
        case o of
            Just a  -> unsafeCastTo gtype a
            Nothing -> throw $ UnknownIdException $ T.unpack id
```
