curl \
    --request POST \
    --url https://example.atlassian.net/gateway/api/compass/v1/metrics \
    --user "$USER_EMAIL:$ATATT3xFfGF0THElxlqWUKVZcgWy2wVvg362SyGYFs9euxaFBp3ymEVN5oet7d79qG3kB6lhVHmJzaHwy0IQjQvUaXUHvEwKRrSozJfZRWvXcsB-bUGuM6EtwcqstRg4e9I-sN49J3u8CEvF0Eg4KBmHq8rSHKuyb4GvMldHKpJSHfFj0GjM9qA=F7083D7A" \
    --header "Accept: application/json" \
    --header "Content-Type: application/json" \
    --data "{
      \"metricSourceId\": \"ari:cloud:compass:...:metric-source/.../...\",
      \"value\": $METRIC_VALUE,
      \"timestamp\": \"$(date -u +'%Y-%m-%dT%H:%M:%SZ')\"
    }"
