
News API
--------

-   R client for newsAPIorg

API key
-------

-   Go to [newsapi.org](https://newsapi.org) and register to get an API key.
-   Save the key as an environment variable

``` r
## my obscured key
NEWSAPI_KEY <- "4345e85e8ae1427480xxxxxxxxxxxxxx"

## save to .Renviron file
cat(
  paste0("NEWSAPI_KEY=", NEWSAPI_KEY),
  append = TRUE,
  fill = TRUE,
  file = file.path("~", ".Renviron")
)
```

Demo
----

-   Get all the news sources.

``` r
src <- get_sources(language = "en")
src
```

-   Pass news source names (IDs) to `get_articles` function.

``` r
df <- lapply(src$id, get_articles)
df <- do.call("rbind", df)
df
```
