
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

`HomeR` is a **resource** (hence the "R"):

> Any \[URL or URI\] denotes something in the world (the "universe of discourse"). These things are called **resources**.

See the [“Resources and Statements” section](https://www.w3.org/TR/rdf11-concepts/#resources-and-statements) of the World Wide Web Consortium (W3C) primer on the Resource Description Framework (RDF).

`mkYesod` is a Template Haskell function. To see the code it generates, use `ddump-splices`.

  * 

<!--stackedit_data:
eyJoaXN0b3J5IjpbNTYyMDkxMTAxLC0xMDY0Mjk4MDQzXX0=
-->