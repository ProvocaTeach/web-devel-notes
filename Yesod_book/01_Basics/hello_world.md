
# Hello World in Yesod #

This covers the ["Basics" chapter of the Yesod book](https://www.yesodweb.com/book/basics).

```haskell
{-# LANGUAGE OverloadedStrings     #-}
{-# LANGUAGE QuasiQuotes           #-}
{-# LANGUAGE TemplateHaskell       #-}
{-# LANGUAGE TypeFamilies          #-}
import           Yesod

data HelloWorld = HelloWorld

mkYesod "HelloWorld" [parseRoutes|
/ HomeR GET
|]

instance Yesod HelloWorld

getHomeR :: Handler Html
getHomeR = defaultLayout [whamlet|Hello World!|]

main :: IO ()
main = warp 3000 HelloWorld
```

`HomeR` is a **resource** (hence the "R").

  * **Resource** ⇒ any

`mkYesod` is a Template Haskell function. To see the code it generates, use `ddump-splices`.

  * 

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NTk2MTIyNDUsLTEwNjQyOTgwNDNdfQ
==
-->