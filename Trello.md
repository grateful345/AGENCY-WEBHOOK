Trello Api token:
ATATT3xFfGF0aXRYQM0Q95lcoWqsYEwV4Xo_tqQjaXBJ1xtP-NT1tGoR9zMoJ4OfhAFF8GMncjTZJW2Vn0fKx2hQslfTTc-dSzyik4NitTMMx9IPRrj_fN5aTrND167SHU4Wv3enJnpjETXFjSvg3KGmNdVNqFknmc0VkLnP-8ZdTik6atWQJxg=D74F7DC5

curl --request GET \
  --url 'https://your-domain.atlassian.net/configuration/retention' \
  --header 'Accept: application/json'

curl --request GET \
  --url 'https://your-domain.atlassian.net/configuration/coverage' \
  --header 'Accept: application/json'
curl --request PUT \
  --url 'https://your-domain.atlassian.net/configuration/coverage' \
  --header 'Accept: application/json' \
  --header 'Content-Type: application/json' \
  --data '{
  "levelByArea": {}
}'
{
  "levelByArea": {}
}
curl --request GET \
  --url 'https://your-domain.atlassian.net/configuration/denylist' \
  --header 'Accept: application/json'
{"actions":["<string>"]}
