
# Hello World in Yesod #

This covers the first part of the ["Basics" chapter of the Yesod book](https://www.yesodweb.com/book/basics).

## Hello World ##

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
## Routing ##

`HomeR` is a **resource** (hence the "R"):

> Any \[URL or URI\] denotes something in the world (the "universe of discourse"). These things are called **resources**.

`mkYesod` is a Template Haskell function. To see the code it generates, use `ddump-splices`.

### Useful sources ###
See the [“Resources and Statements” section](https://www.w3.org/TR/rdf11-concepts/#resources-and-statements) of the World Wide Web Consortium (W3C) primer on the Resource Description Framework (RDF).

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAyNTU0MTUzMCw1NjIwOTExMDEsLTEwNj
QyOTgwNDNdfQ==
-->