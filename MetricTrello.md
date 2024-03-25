curl \
    --request POST \
    --url https://example.atlassian.net/gateway/api/compass/v1/metrics \
    --user "$USER_EMAIL:$ATATT3xFfGF0XmLbrkDjnV3mjB9PvJ51M7nyw7NtrmOSYIdoETrVPQ8ewgxGaWGzVt51nPp6XB0gIdv16qB-cSSfsozIvhi3ntzSgkosHJvYnUy9dJ4pGSeDIZwDAqRE2MI23uiBIc_IYx2E9Oumwgxldv8QAHIx5WChVgy_gaYIyXdGbPZPFt8=F92622C1" \
    --header "Accept: application/json" \
    --header "Content-Type: application/json" \
    --data "{
      \"metricSourceId\": \"ari:cloud:compass:...:metric-source/.../...\",
      \"value\": $METRIC_VALUE,
      \"timestamp\": \"$(date -u +'%Y-%m-%dT%H:%M:%SZ')\"
    }"
