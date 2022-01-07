# githubquery
querying github apis
## Query 1 - hottest top 5 repository in last 30 days 
```
curl -G https://api.github.com/search/repositories       \
    --data-urlencode "q=created:>`date -v-30d '+%Y-%m-%d'`" \
    --data-urlencode "sort=stars"                          \
    --data-urlencode "order=desc"                          \
    -H "Accept: application/vnd.github.preview"            \
    | jq ".items[0,1,2,3,4] | {name, description, language, watchers_count, html_url}"
    ```
 ## Auery 2 
