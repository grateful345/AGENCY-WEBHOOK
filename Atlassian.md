# AGENCY-WEBHOOK
Stripe python gpg key :

gpg --encrypt --recipient 05D02D3D57ABFF46 FILENAME

Key ID: 05D02D3D57ABFF46
Key type: RSA
Key size: 2048 bits
Fingerprint: C330 33E4 B583 FE61 2EDE 877C 05D0 2D3D 57AB FF46
User ID: Stripe <security@stripe.com>
gpg --encrypt --recipient 05D02D3D57ABFF46 FILENAME

Key ID: 05D02D3D57ABFF46
Key type: RSA
Key size: 2048 bits
Fingerprint: C330 33E4 B583 FE61 2EDE 877C 05D0 2D3D 57AB FF46
User ID: Stripe <security@stripe.com>
postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242
{"apikey":"e59a3446-867f-4520-9121-bef3ce8be522"}
Location: /home/linuxbrew
Note: Homebrew is pre-installed on image but not added to PATH.
run the eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)" command
to accomplish this.

Both Xdebug and PCOV extensions are installed, but only Xdebug is enabled.User: postgres
PostgreSQL service is disabled by default.
Use the following command as a part of your job to start the service: 'sudo systemctl start postgresql.service'
MySQL

MySQL 8.0.36-0ubuntu0.22.04.1
User: root
Password: root
MySQL service is disabled by default.
Use the following command as a part of your job to start the service: 'sudo systemctl start mysql.service'
MS SQL

sqlcmd 17.10.0001.1
SqlPackage 162.2.111.2
Cached Tools

Go

1.20.14
1.21.8
1.22.1
Node.js

16.20.2
18.19.1
20.11.1
Python

3.7.17
3.8.18
3.9.18
3.10.13
3.11.8
3.12.2
PyPy

3.7.13 [PyPy 7.3.9]
3.8.16 [PyPy 7.3.11]
3.9.18 [PyPy 7.3.15]
3.10.13 [PyPy 7.3.15]
Ruby

3.1.4
PowerShell Tools

PowerShell 7.4.1
PowerShell Modules

Az: 11.3.1
MarkdownPS: 1.9
Microsoft.Graph: 2.15.0
Pester: 5.5.0
PSScriptAnalyzer: 1.22.0

pip install timml
To update TimML type:

pip install timml --upgrade
To uninstall TimML type:

pip uninstall timml
Experimental and for radial flow only
import numpy as np
import matplotlib.pyplot as plt
import timml as tml
rw = 5
ml = tml.Model3D(kaq=10, z=np.arange(20, -1, -2), kzoverkh=50)
w = tml.LargeDiameterWell(ml, Qw=100, layers=[0, 1, 2, 3, 4], rw=rw)
rf = tml.Constant(ml, 100, 0, 20)
ml.solve()
Number of elements, Number of equations: 2 , 11
..
solution complete
xg = np.linspace(rw, 50, 100)
h = ml.headalongline(xg, 0)
for i in range(10):
    plt.plot(xg, h[i])
plt.xlim(0, 50)
plt.xticks(np.arange(0, 51, 5))
plt.grid()

qx = ml.disvec(rw, 0)[0]
print(qx * 2 * np.pi * rw)
print(np.sum(qx * 2 * np.pi * rw))
[-1.50511966e+01 -1.54865781e+01 -1.66133444e+01 -1.94936336e+01
 -3.32803095e+01 -6.18665346e-03 -2.60712180e-02  2.81040181e-02
  7.22067838e-03  1.38265742e-02]
-99.90816871499192
ml.head(rw, 0)
array([19.7515328 , 19.75153236, 19.75153185, 19.75153275, 19.75153281,
       19.76498845, 19.77043627, 19.77362338, 19.77547235, 19.7763392 ])
from scipy.special import k0
k0(5 / ml.aq.lab[1:])
array([2.06829668e-03, 6.74900159e-06, 3.32024764e-08, 2.57897091e-10,
       3.46416156e-12, 8.82738725e-14, 4.63575933e-15, 5.37054606e-16,
       1.44345016e-16])
ml.aq.eigvec
array([[ 1.00000000e-01,  4.41707654e-01,  4.25325404e-01,
        -3.98470231e-01,  3.61803399e-01, -3.16227766e-01,
         2.62865556e-01, -2.03030724e-01, -1.38196601e-01,
        -6.99596196e-02],
       [ 1.00000000e-01,  3.98470231e-01,  2.62865556e-01,
        -6.99596196e-02, -1.38196601e-01,  3.16227766e-01,
        -4.25325404e-01,  4.41707654e-01,  3.61803399e-01,
         2.03030724e-01],
       [ 1.00000000e-01,  3.16227766e-01, -3.10776816e-17,
         3.16227766e-01, -4.47213595e-01,  3.16227766e-01,
        -2.38891966e-16, -3.16227766e-01, -4.47213595e-01,
        -3.16227766e-01],
       [ 1.00000000e-01,  2.03030724e-01, -2.62865556e-01,
         4.41707654e-01, -1.38196601e-01, -3.16227766e-01,
         4.25325404e-01, -6.99596196e-02,  3.61803399e-01,
         3.98470231e-01],
       [ 1.00000000e-01,  6.99596196e-02, -4.25325404e-01,
         2.03030724e-01,  3.61803399e-01, -3.16227766e-01,
        -2.62865556e-01,  3.98470231e-01, -1.38196601e-01,
        -4.41707654e-01],
       [ 1.00000000e-01, -6.99596196e-02, -4.25325404e-01,
        -2.03030724e-01,  3.61803399e-01,  3.16227766e-01,
        -2.62865556e-01, -3.98470231e-01, -1.38196601e-01,
         4.41707654e-01],
       [ 1.00000000e-01, -2.03030724e-01, -2.62865556e-01,
        -4.41707654e-01, -1.38196601e-01,  3.16227766e-01,
         4.25325404e-01,  6.99596196e-02,  3.61803399e-01,
        -3.98470231e-01],
       [ 1.00000000e-01, -3.16227766e-01, -2.90992345e-16,
        -3.16227766e-01, -4.47213595e-01, -3.16227766e-01,
        -5.07992125e-17,  3.16227766e-01, -4.47213595e-01,
         3.16227766e-01],
       [ 1.00000000e-01, -3.98470231e-01,  2.62865556e-01,
         6.99596196e-02, -1.38196601e-01, -3.16227766e-01,
        -4.25325404e-01, -4.41707654e-01,  3.61803399e-01,
        -2.03030724e-01],
       [ 1.00000000e-01, -4.41707654e-01,  4.25325404e-01,
         3.98470231e-01,  3.61803399e-01,  3.16227766e-01,
         2.62865556e-01,  2.03030724e-01, -1.38196601e-01,
         6.99596196e-02]]

Trello Api token:
ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7

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

  



  curl -v https://mysite.atlassian.net --user me@example.com:ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7
/ NcKhKEbWghsh1bSAUXEO1552

![https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator]

![https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862]

# AGENCY-WEBHOOK
Trello API Token:
ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7

curl -v https://mysite.atlassian.net --user god964v@gmail.com: ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7

curl --request GET \
  --url 'https://api.trello.com/1/actions/{id}?key=APIKey&token= ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7'

curl --request PUT \
  --url 'https://api.trello.com/1/actions/{id}?text={text}&key=APIKey&token= ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7
'

curl --request GET \
  --url 'https://api.trello.com/1/actions/{id}/{field}?key=APIKey&token= ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7'
' \
  --header 'Accept: application/json'

{"id":"5abbe4b7ddc1b351ef961414","idMemberCreator":"5abbe4b7ddc1b351ef961414","data":{"text":"Can never go wrong with bowie","card":{"id":"5abbe4b7ddc1b351ef961414","name":"Bowie","idShort":7,"shortLink":"3CsPkqOF"},"board":{"id":"5abbe4b7ddc1b351ef961414","name":"Mullets","shortLink":"3CsPkqOF"},"list":{"id":"5abbe4b7ddc1b351ef961414","name":"Amazing"}},"type":"commentCard","date":"2020-03-09T19:41:51.396Z","limits":{"reactions":{"perAction":{"status":"ok","disableAt":1000,"warnAt":900},"uniquePerAction":{"status":"ok","disableAt":1000,"warnAt":900}}},"display":{"translationKey":"action_comment_on_card","entities":{"contextOn":{"type":"translatable","translationKey":"action_on","hideIfContext":true,"idContext":"5abbe4b7ddc1b351ef961414"},"card":{"type":"card","hideIfContext":true,"id":"5abbe4b7ddc1b351ef961414","shortLink":"3CsPkqOF","text":"Bowie"},"comment":{"type":"comment","text":"Can never go wrong with bowie"},"memberCreator":{"type":"member","id":"5abbe4b7ddc1b351ef961414","username":"bobloblaw","text":"Bob Loblaw (World)"}}},"memberCreator":{"id":"5abbe4b7ddc1b351ef961414","activityBlocked":false,"avatarHash":"db2adf80c2e6c26b76e1f10400eb4c45","avatarUrl":"https://trello-members.s3.amazonaws.com/5b02e7f4e1facdc393169f9d/db2adf80c2e6c26b76e1f10400eb4c45","fullName":"Bob Loblaw (Trello)","idMemberReferrer":"5abbe4b7ddc1b351ef961414","initials":"BL","username":"bobloblaw"}}

curl --request GET \
  --url 'https://api.trello.com/1/actions/{id}/board?key=APIKey&token= ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7
' \
  --header 'Accept: application/json'

{"id":"5abbe4b7ddc1b351ef961414","name":"Trello Platform Changes","desc":"Track changes to Trello's Platform on this board.","descData":"<string>","closed":false,"idMemberCreator":"5abbe4b7ddc1b351ef961414","idOrganization":"5abbe4b7ddc1b351ef961414","pinned":false,"url":"https://trello.com/b/dQHqCohZ/trello-platform-changelog","shortUrl":"https://trello.com/b/dQHqCohZ","prefs":{"permissionLevel":"org","hideVotes":true,"voting":"disabled","comments":"<string>","selfJoin":true,"cardCovers":true,"isTemplate":true,"cardAging":"pirate","calendarFeedEnabled":true,"background":"5abbe4b7ddc1b351ef961414","backgroundImage":"<string>","backgroundImageScaled":[{"width":100,"height":64,"url":"https://trello-backgrounds.s3.amazonaws.com/SharedBackground/100x64/abc/photo-123.jpg"}],"backgroundTile":true,"backgroundBrightness":"dark","backgroundBottomColor":"#1e2e00","backgroundTopColor":"#ffffff","canBePublic":true,"canBeEnterprise":true,"canBeOrg":true,"canBePrivate":true,"canInvite":true},"labelNames":{"green":"Addition","yellow":"Update","orange":"Deprecation","red":"Deletion","purple":"Power-Ups","blue":"News","sky":"Announcement","lime":"Delight","pink":"REST API","black":"Capabilties"},"limits":{"attachments":{"perBoard":{"status":"ok","disableAt":36000,"warnAt":32400}}},"starred":true,"memberships":"<string>","shortLink":"<string>","subscribed":true,"powerUps":"<string>","dateLastActivity":"<string>","dateLastView":"<string>","idTags":"<string>","datePluginDisable":"<string>","creationMethod":"<string>","ixUpdate":2154,"templateGallery":"<string>","enterpriseOwned":true}

curl --request GET \
  --url 'https://api.trello.com/1/actions/{id}/card?key=APIKey&token= ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7
' \
  --header 'Accept: application/json'

{"id":"5abbe4b7ddc1b351ef961414","address":"<string>","badges":{"attachmentsByType":{"trello":{"board":2154,"card":2154}},"location":true,"votes":2154,"viewingMemberVoted":false,"subscribed":false,"fogbugz":"<string>","checkItems":0,"checkItemsChecked":0,"comments":0,"attachments":0,"description":true,"due":"<string>","start":"<string>","dueComplete":true},"checkItemStates":["<string>"],"closed":true,"coordinates":"<string>","creationMethod":"<string>","dateLastActivity":"2019-09-16T16:19:17.156Z","desc":"👋Hey there,\n\nTrello's Platform team uses this board to keep developers up-to-date.","descData":{"emoji":{}},"due":"<string>","dueReminder":"<string>","idBoard":"5abbe4b7ddc1b351ef961414","idChecklists":[{"id":"5abbe4b7ddc1b351ef961414"}],"idLabels":[{"id":"5abbe4b7ddc1b351ef961414","idBoard":"5abbe4b7ddc1b351ef961414","name":"Overdue","color":"yellow"}],"idList":"5abbe4b7ddc1b351ef961414","idMembers":["5abbe4b7ddc1b351ef961414"],"idMembersVoted":["5abbe4b7ddc1b351ef961414"],"idShort":2154,"labels":["5abbe4b7ddc1b351ef961414"],"limits":{"attachments":{"perBoard":{"status":"ok","disableAt":36000,"warnAt":32400}}},"locationName":"<string>","manualCoverAttachment":false,"name":"👋 What? Why? How?","pos":65535,"shortLink":"H0TZyzbK","shortUrl":"https://trello.com/c/H0TZyzbK","subscribed":false,"url":"https://trello.com/c/H0TZyzbK/4-%F0%9F%91%8B-what-why-how","cover":{"color":"yellow","idUploadedBackground":true,"size":"normal","brightness":"light","isTemplate":false}}

curl --request GET \
  --url 'https://api.trello.com/1/actions/{id}/list?key=APIKey&token= ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7
' \
  --header 'Accept: application/json'

curl --request GET \
  --url 'https://api.trello.com/1/actions/{id}/member?key=APIKey&token= ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7
' \
  --header 'Accept: application/json'

{"id":"5abbe4b7ddc1b351ef961414","activityBlocked":false,"avatarHash":"fc8faaaee46666a4eb8b626c08933e16","avatarUrl":"https://trello-avatars.s3.amazonaws.com/fc8faaaee46666a4eb8b626c08933e16","bio":"👋 I'm a developer advocate at Trello!","bioData":{"emoji":{}},"confirmed":true,"fullName":"Bentley Cook","idEnterprise":"5abbe4b7ddc1b351ef961414","idEnterprisesDeactivated":["<string>"],"idMemberReferrer":"5abbe4b7ddc1b351ef961414","idPremOrgsAdmin":["5abbe4b7ddc1b351ef961414"],"initials":"BC","memberType":"normal","nonPublic":{"fullName":"Bentley Cook","initials":"BC","avatarUrl":"https://trello-members.s3.amazonaws.com/5b02e7f4e1facdc393169f9d/db2adf80c2e6c26b76e1f10400eb4c45","avatarHash":"db2adf80c2e6c26b76e1f10400eb4c45"},"nonPublicAvailable":false,"products":[2154],"url":"https://trello.com/bentleycook","username":"bentleycook","status":"disconnected","aaEmail":"<string>","aaEnrolledDate":"<string>","aaId":"<string>","avatarSource":"gravatar","email":"bcook@atlassian.com","gravatarHash":"0a1e804f6e35a65ae5e1f7ef4c92471c","idBoards":["5abbe4b7ddc1b351ef961414"],"idOrganizations":["5abbe4b7ddc1b351ef961414"],"idEnterprisesAdmin":["5abbe4b7ddc1b351ef961414"],"limits":{"status":"ok","disableAt":36000,"warnAt":32400},"loginTypes":["password"],"marketingOptIn":{"optedIn":false,"date":"2018-04-26T17:03:25.155Z"},"messagesDismissed":{"name":"ad-security-features","count":"<string>","lastDismissed":"2019-03-11T20:19:46.809Z","_id":"5abbe4b7ddc1b351ef961414"},"oneTimeMessagesDismissed":["<string>"],"prefs":{"timezoneInfo":{"offsetCurrent":360,"timezoneCurrent":"CST","offsetNext":300,"dateNext":"2020-03-08T08:00:00.000Z","timezoneNext":"CDT"},"privacy":{"fullName":"public","avatar":"public"},"sendSummaries":true,"minutesBetweenSummaries":60,"minutesBeforeDeadlineToNotify":1440,"colorBlind":true,"locale":"en-AU","timezone":"America/Chicago","twoFactor":{"enabled":true,"needsNewBackups":false}},"trophies":["<string>"],"uploadedAvatarHash":"dac3ad49ff117829dd63a79bb2ea3426","uploadedAvatarUrl":"https://trello-avatars.s3.amazonaws.com/dac3ad49ff117829dd63a79bb2ea3426","premiumFeatures":["<string>"],"isAaMastered":false,"ixUpdate":2154,"idBoardsPinned":["5abbe4b7ddc1b351ef961414"]}

curl --request GET \
  --url 'https://api.trello.com/1/actions/{id}/member?key=APIKey&token= ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7
' \
  --header 'Accept: application/json'

// This code sample uses the 'Unirest' library:
// http://unirest.io/php.html
$headers = array(
  'Accept' => 'application/json'
);

$query = array(
  'key' => 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242',
  'token' => 'ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7
'
);

$response = Unirest\Request::get(
  'https://api.trello.com/1/actions/{id}/memberCreator',
  $headers,
  $query
);

var_dump($response)

curl --request GET \
  --url https://api.trello.com/1/actions/id?reactions=true

{
  "id": "5afc2c98bb0aa3d078e30be4",
  "reactions": [
    {
      "id": "5afeec8fb0850e36938e465b",
      "idMember": "54f8181e733cf3c45ec056be",
      "idModel": "5afc2c98bb0aa3d078e30be4",
      "idEmoji": "1F64C",
      "member": {
        "id": "54f8181e733cf3c45ec056be",
        "avatarHash": "0fdb1227362c631f7dddaebedbe13f07",
        "avatarUrl": "https://trello-avatars.s3.amazonaws.com/0fdb1227362c631f7dddaebedbe13f07",
        "fullName": "Felix Haehnel",
        "initials": "FH",
        "username": "fhaehnel"
      },
      "emoji": {
        "unified": "1F64C",
        "native": "🙌",
        "name": "PERSON RAISING BOTH HANDS IN CELEBRATION",
        "skinVariation": null,
        "shortName": "raised_hands"
      }
    }
  ]
} 

curl --request GET \
  --url https://api.trello.com/1/cards/id?actions=commentCard&action_reactions=true

curl https://api.trello.com/1/boards/BdarzfKF/?fields=id&actions=addAttachmentToCard&actions_limit=2&action_fields=idMemberCreator&action_memberCreator_fields=fullName

curl --request PUT \
  --url 'https://api.trello.com/1/actions/{id}/text?value={value}&key=APIKey&token= ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7'

host:~ test$ echo $JAVA_HOME
/Library/Java/JavaVirtualMachines/jdk1.8.0_65.jdk/Contents/Home
host:~ test$ vi ~/.bash_profile
Add the following lines at the end of the file:
1
2
3
JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0.0_91.jdk/Contents/Home
export JAVA_HOME
export PATH=$PATH:$JAVA_HOME/bin
The path in Line 1 will be the path for the JDK on your system.
For Mac OS X this is usually /Library/Java/JavaVirtualMachines/1.8.x.jdk. On Linux it may be /usr/local/jdk or similar.
You can choose to setup your machine to quickly change between different java versions by following the instructions [here](https://developer.atlassian.com/server/framework/atlassian-sdk/how-to-quickly-switch-between-installed-java-versions-in-terminal/)
Save and close the file.
Enter the following at the command line to pick up your changes:
1
host:~ test$ source ~/.bash_profile
Verify you are now seeing the correct result when you enter the command javac -version in terminal
1
2
host:~ test$ javac -version
javac 1.8.0_91 
Step 2: Download and install the SDK
There are native installers for a number of operating systems available, as well as a TGZ (GZipped tar file) which can be used for manual installation.  
Last updated 04 Dec 2015
By downloading and/or using this SDK you agree to the [Atlassian Developer Terms](https://developer.atlassian.com/server/framework/atlassian-sdk/install-the-atlassian-sdk-on-a-linux-or-mac-system/Atlassian-Developer-Terms_37879876.html)
Select the installation instructions that best suit you
Mac OSX
PKG File
[Download the PKG file](https://marketplace.atlassian.com/download/plugins/atlassian-plugin-sdk-mac).
Double click the PKG file to launch the installer.
Follow the prompts to complete the installation.
[Next: Verify that you have set up the SDK correctly](https://developer.atlassian.com/display/DOCS/Install+the+Atlassian+SDK+on+a+Linux+or+Mac+system#step-3--verify-that-you-have-set-up-the-sdk-correctly)
Homebrew
Open a Terminal window and add the Atlassian "Tap" to your Brew using the command:
1
brew tap atlassian/tap
Then install the SDK using the atlassian/tap command:
1
brew install atlassian/tap/atlassian-plugin-sdk
[Next: Verify that you have set up the SDK correctly](https://developer.atlassian.com/display/DOCS/Install+the+Atlassian+SDK+on+a+Linux+or+Mac+system#step-3--verify-that-you-have-set-up-the-sdk-correctly)
Debian, Ubuntu Linux
On a Debian-based Linux system like Ubuntu, you can install the SDK using apt-get or aptitude:
First, set up the Atlassian SDK repositories:
1
sudo sh -c 'echo "deb https://packages.atlassian.com/debian/atlassian-sdk-deb/ stable contrib" >>/etc/apt/sources.list'
Download the public key using curl or wget:
1
wget https://packages.atlassian.com/api/gpg/key/public    
Add the public key to apt to verify the package signatures automatically:
1
sudo apt-key add public   
Then, run the install:
1
2
sudo apt-get update
sudo apt-get install atlassian-plugin-sdk
[Next: Verify that you have set up the SDK correctly](https://developer.atlassian.com/server/framework/atlassian-sdk/install-the-atlassian-sdk-on-a-linux-or-mac-system/#step-3--verify-that-you-have-set-up-the-sdk-correctly)
Red Hat Enterprise Linux, CentOS, Fedora (RPM)
To install on systems that use the Yum package manager:
Create the repo file in your /etc/yum.repos.d/ folder:
1
sudo vi /etc/yum.repos.d/artifactory.repo
Configure the repository details:
1
2
3
4
5
[Artifactory]
name=Artifactory
baseurl=https://packages.atlassian.com/yum/atlassian-sdk-rpm/
enabled=1
gpgcheck=0
Install the SDK:
1
2
3
sudo yum clean all
sudo yum updateinfo metadata
sudo yum install atlassian-plugin-sdk
As always,[Verify that you have set up the SDK correctly.](https://developer.atlassian.com/server/framework/atlassian-sdk/install-the-atlassian-sdk-on-a-linux-or-mac-system/#step-3--verify-that-you-have-set-up-the-sdk-correctly)
.tgz File
To install the latest version of SDK, do the following:
[Download a TGZ (GZipped tar file) of the SDK](https://marketplace.atlassian.com/download/plugins/atlassian-plugin-sdk-tgz)
Locate the downloaded SDK file. 
Extract the file to your local directory.
1
sudo tar -xvzf atlassian-plugin-sdk-4.0.tar.gz -C /opt
Rename the extracted folder to  atlassian-plugin-sdk .
1
sudo mv /opt/atlassian-plugin-sdk-4.0 /opt/atlassian-plugin-sdk 
If you are comfortable working with symbolic links, you can set up a symbolic link instead of renaming the directory.
[Next: Verify that you have set up the SDK correctly](https://developer.atlassian.com/display/DOCS/Install+the+Atlassian+SDK+on+a+Linux+or+Mac+system#step-3--verify-that-you-have-set-up-the-sdk-correctly)
Step 3: Verify that you have set up the SDK correctly
Open a terminal window and run the following command:
1
atlas-version
You should see something similar to:
1
2
3
4
5
6
7
8
9
10
11
12
13
14
ATLAS Version:    6.2.9
ATLAS Home:       /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec
ATLAS Scripts:    /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec/bin
ATLAS Maven Home: /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec/apache-maven-3.2.1
AMPS Version:     6.2.6
--------
Executing: /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec/apache-maven-3.2.1/bin/mvn --version -gs /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec/apache-maven-3.2.1/conf/settings.xml
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=256M; support was removed in 8.0
Apache Maven 3.2.1 (ea8b2b07643dbb1b84b6d16e1f08391b666bc1e9; 2014-02-15T04:37:52+10:00)
Maven home: /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec/apache-maven-3.2.1
Java version: 1.8.0_45, vendor: Oracle Corporation
Java home: /Library/Java/JavaVirtualMachines/jdk1.8.0_45.jdk/Contents/Home/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "mac os x", version: "10.11.6", arch: "x86_64", family: "mac"
curl https://api.trello.com/1/boards/k7hfpqQm/lists?fields=all&filter=all

25
[
  {
    "id": "5ac61a2e05fae550b0d45c94",
    "name": "Prompts",
    "closed": false,
    "idBoard": "5ac61a2e05fae550b0d45c93",
    "pos": 98303,
    "subscribed": null,
    "limits": {
      "cards": {
        "openPerList": {
          "status": "ok",
          "disableAt": 5000,
          "warnAt": 4500
        },
        "totalPerList": {
          "status": "ok",
          "disableAt": 1000000,
          "warnAt": 900000
        }
      }
    },
    "creationMethod": null
  }
]

TrelloID:
{"id":"5abbe4b7ddc1b351ef961414"}

curl --request GET \
  --url 'https://api.trello.com/1/actions/{id}/organization?key=APIKey&token= ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7' \
  --header 'Accept: application/json'

curl --request GET \
  --url 'https://api.trello.com/1/actions/{id}/organization?key=APIKey&token= ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7' \
  --header 'Accept: application/json'

// This sample uses Atlassian Forge
// https://developer.atlassian.com/platform/forge/
import api, { route } from "@forge/api";

var bodyData = `{
  "body": {
    "content": [
      {
        "content": [
          {
            "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque eget venenatis elit. Duis eu justo eget augue iaculis fermentum. Sed semper quam laoreet nisi egestas at posuere augue semper.",
            "type": "text"
          }
        ],
        "type": "paragraph"
      }
    ],
    "type": "doc",
    "version": 1
  },
  "visibility": {
    "identifier": "Administrators",
    "type": "role",
    "value": "Administrators"
  }
}`;

const response = await api.asUser().requestJira(route`/rest/api/3/issue/{ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7}/comment/{id}`, {
  method: 'PUT',
  headers: {
    'Accept': 'application/json',
    'Content-Type': 'application/json'
  },
  body: bodyData
});

console.log(`Response: ${response.status} ${response.statusText}`);
console.log(await response.json());

// This sample uses Atlassian Forge
// https://developer.atlassian.com/platform/forge/
import api, { route } from "@forge/api";

var bodyData = `{
  "body": {
    "content": [
      {
        "content": [
          {
            "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque eget venenatis elit. Duis eu justo eget augue iaculis fermentum. Sed semper quam laoreet nisi egestas at posuere augue semper.",
            "type": "text"
          }
        ],
        "type": "paragraph"
      }
    ],
    "type": "doc",
    "version": 1
  },
  "visibility": {
    "identifier": "Administrators",
    "type": "role",
    "value": "Administrators"
  }
}`;

const response = await api.asUser().requestJira(route`/rest/api/3/issue/{ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7}/comment/{id}`, {
  method: 'PUT',
  headers: {
    'Accept': 'application/json',
    'Content-Type': 'application/json'
  },
  body: bodyData
});

console.log(`Response: ${response.status} ${response.statusText}`);
console.log(await response.json());

git clone https://github.com/curl/curl.git

git clone https://github.com/Microsoft/vcpkg.git
cd vcpkg
./bootstrap-vcpkg.sh
./vcpkg integrate install
vcpkg install curl[tool]

1
2
3
4
$ node -v
v12.12.0
$ npm -v
6.11.3
Install atlas-connect by running:
1
npm install -g atlas-connect
Verify the installation by running:
1
atlas-connect --help
If ACE installed successfully, you'll see the following:
1
2
3

<atlassian-plugin name="Hello World Servlet" key="example.plugin.helloworld" plugins-version="2">
    <plugin-info>
        <description>A basic Servlet module test - says "Hello World!</description>
        <vendor name="Atlassian Software Systems" url="http://www.atlassian.com"/>
        <version>1.0</version>
    </plugin-info>

    <servlet name="Hello World Servlet" key="helloWorld" class="com.example.myplugins.helloworld.HelloWorldServlet">
        <description>Says Hello World, Australia or your name.</description>
        <url-pattern>/helloworld</url-pattern>
        <init-param>
            <param-name>defaultName</param-name>
            <param-value>Australia</param-value>
        </init-param>
    </servlet>
</atlassian-plugin>

5

<component key="jiraPluginComponent" class="com.example.JiraPluginComponent" 
           interface="com.example.PluginComponent" application="jira" />
<component key="confluencePluginComponent" class="com.example.ConfluencePluginComponent"  
           interface="com.example.PluginComponent" application="confluence" />

7

<component-import 
  key="appProps" 
  interface="com.atlassian.sal.api.ApplicationProperties"/>

<servlet key="myServlet" class="class:com.example.MyServlet" />
Since the "class" prefix is the default, you could also configure the Servlet via:
1
<servlet key="myServlet" class="com.example.MyServlet" />

9
10 1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
var GRAY_ICON = 'https://cdn.hyperdev.com/us-east-1%3A3d31b21c-01a0-4da2-8827-4bc6e88b7618%2Ficon-gray.svg';

window.TrelloPowerUp.initialize({
  'attachment-sections': function(t, options){
    // options.entries is a list of the attachments for this card
    // you can look through them and 'claim' any that you want to
    // include in your section.

    // we will just claim urls for Yellowstone
    var claimed = options.entries.filter(function (attachment) {
      return attachment.url.indexOf('http://www.nps.gov/yell/') === 0;
    });

    // you can have more than one attachment section on a card
    // you can group items together into one section, have a section
    // per attachment, or anything in between.
    if (claimed && claimed.length > 0) {
      // if the title for your section requires a network call or other
      // potentially lengthy operation you can provide a function for the title
      // that returns the section title. If you do so, provide a unique id for
      // your section
      return [{
        id: 'Yellowstone', // optional if you aren't using a function for the title
        claimed: claimed,
        icon: GRAY_ICON, // Must be a gray icon, colored icons not allowed.
        title: 'Example Attachment Section: Yellowstone',
        content: {
          type: 'iframe',
          url: t.signUrl('./section.html', {
            arg: 'you can pass your section args here'
          }),
          height: 230
        }
      }];
    } else {
      return [];
    }
  }
});
./section.html looks like:
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
<html>
  <head>
    <link rel="stylesheet" href="https://p.trellocdn.com/power-up.min.css">
    <script src="https://p.trellocdn.com/power-up.min.js"></script>
  </head>
  <body>
    <div id="content">
      <p>Tips for using attachment-sections</p>
      <ol>
        <li>Make sure your section feels at home on the card. It should fit in with the rest of the card and not stick out.</li>
        <li>You can specify a height when you claim the section, and also use t.sizeTo() to make sure your section is the perfect height.</li>
        <li>Try to keep the height of your sections to a minimum.</li>
        <li>It should be obvious to the user what attachments went into your section. They shouldn't be left wondering where one of their attachments disappeared to.</li>
      </ol>
      <p class="u-quiet">Claimed attachment urls: <span id="urls"></span></p>
    </div>
    <script src="./js/section.js"></script>
  </body>
</html>
./js/section.js looks like:
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
var t = window.TrelloPowerUp.iframe();

// you can access arguments passed to your iframe like so
var arg = t.arg('arg');

t.render(function(){
  // make sure your rendering logic lives here, since we will
  // recall this method as the user adds and removes attachments
  // from your section
  t.card('attachments')
  .get('attachments')
  .filter(function(attachment){
    return attachment.url.indexOf('http://www.nps.gov/yell/') == 0;
  })
  .then(function(yellowstoneAttachments){

window.TrelloPowerUp.initialize({
  'authorization-status': function(t, options){
    // return a promise that resolves to the object with
    // a property 'authorized' being true/false
    // you can also return the object synchronously if you know
    // the answer synchronously
    return new TrelloPowerUp.Promise((resolve) => resolve({ authorized: true }));
  }
});

window.TrelloPowerUp.initialize({
  'show-authorization': function(t, options){
    // return what to do when a user clicks the 'Authorize Account' link
    // from the Power-Up gear icon which shows when 'authorization-status'
    // returns { authorized: false }
    // in this case we would open a popup
    return t.popup({
      title: 'My Auth Popup',
      url: './authorize.html',
      height: 140,
    });
  }
});

window.TrelloPowerUp.initialize({
  'show-authorization': function(t, options){
    // return what to do when a user clicks the 'Authorize Account' link
    // from the Power-Up gear icon which shows when 'authorization-status'
    // returns { authorized: false }
    // in this case we would open a popup
    return t.popup({
      title: 'My Auth Popup',
      url: './authorize.html',
      height: 140,
    });
  }
});

 Usage: atlas-connect [options] [command]


 Commands:

  new [name]  create a new Atlassian app
  help [cmd]  display help for [cmd]

 Options:

  -h, --help     output usage information
  -V, --version  output the version number
The REST endpoint is /wiki/rest/api/search
The CQL looks like this:
1
id != 0 order by lastmodified desc
You'll use limit=1 to make sure you only get one result: the most recently updated piece of content.
Before you begin
Ensure you have installed all the tools you need for Confluence Connect app development by [Getting set up with Atlassian Connect Express (ACE)](https://developer.atlassian.com/cloud/confluence/getting-set-up-with-ace/):
Get a cloud development site.
Enable development mode in your site.
Install ACE.
You'll want to add some content to search and make sure you have cURL installed:
Add pages, blog posts, and other content to your Confluence instance.
Install cURL if necessary. You can check whether it is installed by typing:
1
curl --version
Call the REST API using cURL
You can make REST API calls from the command line using cURL. This is a good way to get familiar with the behavior of the APIs.
Authentication
To make REST API calls using cURL or from a script, you must authenticate with your Atlassian email and API token encoded together in the base64 format. You can use an online tool or an application such as base64 (macOS/Linux) or certutil (Windows) to encode the string into base64 format.
[Generate an API token](https://id.atlassian.com/manage/api-tokens) for your Atlassian account.
Build a string with your Atlassian email address and the API token separated by a colon. Example:
1
grateful345i@gmail.com:616616ss$$$
Use an online tool or an application to encode the string into base64 format. The result is a string of letters and numbers like this:
1
eW91cl9lbWFpbEBhdGxhc3NpYW4ubmV0OjEyMzQ1Njc=
You'll use this encoded string in the Authorization header when you make the call.
Making the call
Once you have encoded your credentials, you can use cURL to make a call to the REST API. The syntax is:
1
2
3
curl --request <method> '<url>?<parameters>' \
--header 'Accept: application/json' \
--header 'Authorization: Basic < ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7 >'
You'll be making a GET request to the search REST API using parameters to specify a CQL query and a limit to the number of results. Here are the steps:
Build a URL made up of your Atlassian site plus the path to the REST endpoint. For this tutorial, use the search endpoint. For example:
1
https://your_site_name.atlassian.net/wiki/rest/api/search
Add the limit and cql parameters to specify the results you want. Remember to URL-encode the spaces by changing them to %20 characters:
1
?limit=1&cql=id%20!=%200%20order%20by%20lastmodified%20desc
Finally, build the entire cURL command using the URL, parameters, and your encoded credentials. Specify the GET request method. For example:
1
2
3
4
curl --request GET 'https://your_site_name.atlassian.net/wiki/rest/api/search?limit=1&cql=id%20!=%200%20order%20by%20lastmodified%20desc' \
--header 'Accept: application/json' \
--header 'Authorization: Basic eW91cl9lbWFpbEBhdGxhc3NpYW4ubmV0OjEyMzQ1Njc= / ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7'

The lines have been broken here for readability using a backslash (\), but for now just put the entire command on a single line.
Type or paste the command onto the command line and press Enter.
If you don't get the results you expect, check the syntax of the command. Spaces, line breaks, or typos can sometimes cause errors that look like authentication failures or other problems.
Create a new app
To make REST API calls from Connect, you'll use the "Hello, World" app that the Connect framework creates. You'll atlas-connect to create the app framework, which is a directory called rest-tutorial that contains all the basic components of a Connect app.
From the command line, go into a directory where you'd like to work, and type:
1
atlas-connect new rest-tutorial
Select Confluence in the menu.
When the command finishes, go into the rest-tutorial directory and run npm install to install any dependencies for the app.
Add a credentials.json file in your app directory with your information:
your-confluence-domain: Use the domain of your cloud development site (for example, https://your-domain.atlassian.net/).
username: Use the email address of your [god964v@gmail.com / grateful345i@gmail.com](https://confluence.atlassian.com/cloud/atlassian-account-for-users-873871199.html).
password: Specify the [ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7
](https://confluence.atlassian.com/x/Vo71Nw).
1
2
3
4
5
6
7
8
9
10
11
12
{
   "hosts" : {
      "<your-confluence-domain>": {
         "product" : "confluence",
         "username" : "<grateful345i@gmail.com>",
         "password" : "< ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7
>"
      }
   },
   "ngrok": {
      "authtoken": "2e1uqTiGDrl51lJjY9y8sSCKPK2_4kcsLDeikKnwNAjspHsSo"
   }
}
If you've already done the [Getting started](https://developer.atlassian.com/cloud/confluence/getting-started/) tutorial, you can just copy over the credentials.json file from that directory.
The "Hello world" app provided by atlas-connect includes a generalPages module, a route handler, and a view already. You'll use these existing components to make a REST API call and display some of the results. If you're not familiar with how the view displays variables from the route handler, you can learn by doing the [Creating a general page](https://developer.atlassian.com/cloud/confluence/creating-a-general-page/) tutorial.
Make a REST call from the route handler
In a Connect route handler, you can grab the clientKey from the context and use it to build an httpClient for making requests to the REST API. Connect builds headers for you and takes care of authentication using the credentials in credentials.json. In this example, you'll make the same REST API call you made in the cURL example, parse the JSON, and display the title of the updated page. You'll access the title using contents.results[0].title and store it in a variable called page_title for display by the view.
Edit index.js (inside the routes directory), replacing the existing app.get() function with the following code:
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
 app.get('/hello-world', addon.authenticate(), (req, res) => {

         const clientKey = req.context.clientKey;
         const httpClient = addon.httpClient({
             clientKey: clientKey  
         });

         httpClient.get(
             '/rest/api/content/search?limit=1&cql= id != 0 order by lastmodified desc',
             function(err, response, contents){
                 if(err || (response.statusCode < 200 || response.statusCode > 299)) {
                     console.log(err);
                     res.render('<strong>An error has occurred : '+ response.statusCode +'</strong>');
                 }
                 contents = JSON.parse(contents);
                 console.log(contents);
              
                 let page_title;
             
                 if(contents.size > 0){
                   page_title = contents.results[0].title;
                 }else{
                   page_title = "Error: no results";
                 }

                 res.render(
                   'hello-world.hbs', 
                   {
                     title: 'Atlassian Connect', 
                     updated_page: page_title
                   });
             }
         );   
     });
Edit hello-world.hbs (inside the views directory), adding the following line after the Welcome to {{title}} line:
1
      <p>The most recently updated page is: <b>{{updated_page}}</b>!</p>
In the rest-tutorial directory, type npm start on the command line to start the app.
Navigate to your Confluence instance and click on 'Hello World' under Apps. You should see the title of the most recently updated piece of content (and it should match the result you got with cURL).
Because Connect escapes the URL for you, you don't have to replace the spaces with %20 and the URL is much easier to read.
Make a REST call from the view
You can use the Atlassian JavaScript API to make REST calls directly from the view. In this part of the tutorial, you'll use the AP.request() function to make the call, grabbing
some information from the JSON response. You'll change the innerHTML of a <div> to display the information in the view.
If the app is running, stop it.
Edit hello-world.hbs and add the following code after the {{updated_page}} line that you added in the previous section:
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
  <div id="more_info"></div>
  <script>
     AP.request({
       url: '/rest/api/content/search?limit=1&cql=id!=0 order by lastmodified desc',
        success: function(response) {
          response = JSON.parse(response);
          if(response.size > 0){
            document.getElementById('more_info').innerHTML = 
              '<ul><li>Type: ' + response.results[0].type + 
              '</li><li>ID: ' + response.results[0].id + 
              '</li></ul>'
            } else {
              document.getElementById('more_info').innerHTML = "<b>No results found.</b>";
            }
        },
        error: function() {
          console.log(arguments);
        }  
      });
  </script>
  

1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
{
  "statusCode": 404,
  "data": {
    "authorized": false,
    "valid": false,
    "errors": [
      {
        "message": {
          "translation": "This is an example error message.",
          "args": []
        }
      }
    ],
    "successful": false
  },
  "message": "This is an example error message."
}

GET /wiki/rest/api/content/{id}?expand=space,metadata.labels

GET /wiki/rest/api/content?start=4&limit=10


 POST /jira-issue_created?user_id=admin&user_key=admin HTTP/1.1
 Authorization: JWT ...
 Atlassian-Connect-Version: x.x
 Content-Type: application/json
 {
   timestamp: 1426661049725,
   webhookEvent: 'jira:issue_created',
   ...
 }
 
 {
   "timestamp"
   "event"
   "user": {
     // See User shape in the linked document
   },
   "issue": {
     // See Issue shape in the linked document
   },
   "changelog" : {
     // See Changelog shape in the linked document
   },
   "comment" : {
     // See Comment shape in in the linked document
   }
 }
 https://service.example.com/webhook/{ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7}
If an issue with the key EXA-1 triggers a webhook, then the URL that will be used is:
1
https://service.example.com/webhook/EXA-1

1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
{
   "url": "https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862",
   "webhooks": [
      {
         "jqlFilter": "project = PRJ AND status = Done",
         "events": ["jira:issue_created", "jira:issue_updated"]
      },
      {
         "jqlFilter": "status = Done",
         "events": ["jira:issue_updated"]
      },
      {
         "jqlFilter": "myClause = something",
         "events": ["jira:issue_deleted"]
      }
   ]
}
This request will try to register three webhooks. The response will be a JSON array with a result for every webhook. In this case, we will likely succeed in registering the first two, while the third one will fail due to the unsupported JQL clause. The response will then look like this:
1
2
3
4
5
6
7
8
9
10
11
[
  {
    "createdWebhookId": 1000
  },
  {
    "createdWebhookId": 1001
  },
  {
    "errors": ["The clause myClause is unsupported"]
  }
]
ill contain the additional matchedWebhookIds root level property:
1
2
3
4
{
   ... usual webhook data ...,
   "matchedWebhookIds": [1000, 1001]
}
Example Connect app using this REST API
An example Connect app that uses the REST API to register webhooks, fetch registered webhooks, delete them, and handle them, can be found [here](https://bitbucket.org/atlassianlabs/webhook-management-example-app).
Webhooks authentication for OAuth 2.0 apps
Webhooks for OAuth 2.0 apps are secured by bearer authentication. The token is present in the Authorization header and is signed with the app's client secret. Remember to verify the token to keep your integration secure. The use of a library to verify the token is recommended. A list of suitable libraries can be found on the [JWT website](https://jwt.io/).
Registering a webhook using the Jira REST API (other integrations)
Starting from July 2024, this type of integration will have a limit of 100 active admin webhooks.
Webhook JSON format
Example of a valid request body
1
2
3
4
5
6
7
8
9
10
11
12
13
14
 {
  "name": "my first webhook via rest",
  "description": "description of my first webhook",
  "url": "https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862",
  "events": [
    "jira:issue_created",
    "jira:issue_updated"
  ],
  "filters": {
    "issue-related-events-section": "Project = JRA AND resolution = Fixed"
  },
  "excludeBody" : false,
  "secret" : "G8j4166a5OkXRD4WbqV3"
}
Where secret is an optional string used to [generate a signature](https://developer.atlassian.com/cloud/jira/platform/webhooks/#secure-admin-webhooks) and verify incoming webhook payloads. You can’t retrieve your secret after you generate it - if you lose it, you have to get a new one.
Example of a valid response body
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
 {
  "name": "my first webhook via rest",
  "description": "description of my first webhook",
  "url": "https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862",
  "excludeBody": false,
  "events": [
    "jira:issue_created",
    "jira:issue_updated"
  ],
  "filters": {
    "issue-related-events-section": "Project = JRA AND resolution = Fixed"
  },
  "enabled": true,
  "self": "https://your-domain.atlassian.net/rest/webhooks/1.0/webhook/72",
  "lastUpdated": 1706692865788,
  "isSigned": true
}

curl --user username:password \
    -X GET \
    -H "Content-Type: application/json" \
    https://your-domain.atlassian.net/rest/webhooks/1.0/webhook
To get a specific webhook by its ID, perform a GET with the following URL: https://your-domain.atlassian.net/rest/webhooks/1.0/webhook/{webhookId}
The following would get a webhook with an ID of 72:
1
2
3
4
curl --user username:password \
    -X GET \
    -H "Content-Type: application/json" \
    https://your-domain.atlassian.net/rest/webhooks/1.0/webhook/72

Stripe python gpg key :

gpg --encrypt --recipient 05D02D3D57ABFF46 FILENAME

Key ID: 05D02D3D57ABFF46
Key type: RSA
Key size: 2048 bits
Fingerprint: C330 33E4 B583 FE61 2EDE 877C 05D0 2D3D 57AB FF46
User ID: Stripe <security@stripe.com>
gpg --encrypt --recipient 05D02D3D57ABFF46 FILENAME

Key ID: 05D02D3D57ABFF46
Key type: RSA
Key size: 2048 bits
Fingerprint: C330 33E4 B583 FE61 2EDE 877C 05D0 2D3D 57AB FF46
User ID: Stripe <security@stripe.com>
postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242 {"apikey":"e59a3446-867f-4520-9121-bef3ce8be522"}
Location: /home/linuxbrew
Note: Homebrew is pre-installed on image but not added to PATH. run the eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)" command to accomplish this.

Both Xdebug and PCOV extensions are installed, but only Xdebug is enabled.User: postgres PostgreSQL service is disabled by default.
Use the following command as a part of your job to start the service: 'sudo systemctl start postgresql.service' MySQL

MySQL 8.0.36-0ubuntu0.22.04.1
User: root
Password: root
MySQL service is disabled by default.
Use the following command as a part of your job to start the service: 'sudo systemctl start mysql.service' MS SQL

sqlcmd 17.10.0001.1
SqlPackage 162.2.111.2
Cached Tools

Go

1.20.14
1.21.8
1.22.1
Node.js

16.20.2
18.19.1
20.11.1
Python

3.7.17
3.8.18
3.9.18
3.10.13
3.11.8
3.12.2
PyPy

3.7.13 [PyPy 7.3.9]
3.8.16 [PyPy 7.3.11]
3.9.18 [PyPy 7.3.15]
3.10.13 [PyPy 7.3.15]
Ruby

3.1.4
PowerShell Tools

PowerShell 7.4.1
PowerShell Modules

Az: 11.3.1
MarkdownPS: 1.9
Microsoft.Graph: 2.15.0
Pester: 5.5.0
PSScriptAnalyzer: 1.22.0

i_pad
i key pad
XOR
64 bytes
<= 64 bytes
key
o_pad
o key pad
XOR
64 bytes
<= 64 bytes
i key pad
message
hash sum 1
o key pad
hash sum 1
hash sum 2
SHA1 – 1st pass
SHA1 – 2nd pass
64 bytes
20 

// This sample uses Atlassian Forge
// https://developer.atlassian.com/platform/forge/
import api, { route } from "@forge/api";

const response = await api.asUser().requestJira(route`/rest/api/3/issue/{issueIdOrKey}/comment/{5b10a2844c20165700ede21g}`, {
  headers: {
    'Accept': 'application/json'
  }
});

console.log(`Response: ${response.status} ${response.statusText}`);
console.log(await response.json());

signature: a4771c39fbe90f317c7824e83ddef3caae9cb3d976c214ace1f2937e133263c9
X-Hub-Signature: sha256=a4771c39fbe90f317c7824e83ddef3caae9cb3d976c214ace1f2937e133263c9
Examples
You can use your programming language of choice to implement HMAC verification in your code. Following are some examples showing how an implementation might look in various programming languages. Note that these examples assume that Jira is using the sha256 hash algorithm. Jira might start using another method for the HMAC in the future. The example code here will start failing if this happens.
Java example
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
import javax.crypto.Mac;
import javax.crypto.spec.SecretKeySpec;
import java.nio.charset.StandardCharsets;
import java.security.InvalidKeyException;
import java.security.MessageDigest;
import java.security.NoSuchAlgorithmException;
import java.util.HexFormat;

public class Main {
    public static void main(String[] args) throws NoSuchAlgorithmException, InvalidKeyException {
        final String secret = "It's a Secret to Everybody";
        final String payload = "Hello World!";
        final String givenSignature = "sha256=a4771c39fbe90f317c7824e83ddef3caae9cb3d976c214ace1f2937e133263c9";

        final SecretKeySpec keySpec = new SecretKeySpec(secret.getBytes(StandardCharsets.UTF_8), "HmacSHA256");
        final Mac mac = Mac.getInstance("HmacSHA256");
        mac.init(keySpec);

        final byte[] digest = mac.doFinal(payload.getBytes(StandardCharsets.UTF_8));
        final HexFormat hex = HexFormat.of();

        final String calculatedSignature = "sha256=" + hex.formatHex(digest);

        if (!MessageDigest.isEqual(calculatedSignature.getBytes(), givenSignature.getBytes())) {
            System.out.println("Signatures do not match\nExpected signature:" +
                    calculatedSignature + "\nActual: signature: " + givenSignature);
        } else {
            System.out.println("Signatures match");
        }
    }
}
Python example
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
import hashlib
import hmac

secret = "It's a Secret to Everybody"
payload = "Hello World!"
given_signature = "sha256=a4771c39fbe90f317c7824e83ddef3caae9cb3d976c214ace1f2937e133263c9"

hash_object = hmac.new(
    secret.encode("utf-8"),
    msg=payload.encode("utf-8"),
    digestmod=hashlib.sha256,
)
calculated_signature = "sha256=" + hash_object.hexdigest()

if not hmac.compare_digest(calculated_signature, given_signature):
    print(
        "Signatures do not match\nExpected signature:"
        f" {calculated_signature}\nActual: signature: {given_signature}"
    )
else:
    print("Signatures match")
Adding
pip install timml
To update TimML type:

{"author":{"accountId":"5b10a2844c20165700ede21g","active":false,"displayName":"Mia Krystof","self":"https://your-domain.atlassian.net/rest/api/3/user?accountId=5b10a2844c20165700ede21g"},"body":{"type":"doc","version":1,"content":[{"type":"paragraph","content":[{"type":"text","text":"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque eget venenatis elit. Duis eu justo eget augue iaculis fermentum. Sed semper quam laoreet nisi egestas at posuere augue semper."}]}]},"created":"2021-01-17T12:34:00.000+0000","id":"10000","self":"https://your-domain.atlassian.net/rest/api/3/issue/10010/comment/10000","updateAuthor":{"accountId":"5b10a2844c20165700ede21g","active":false,"displayName":"Mia Krystof","self":"https://your-domain.atlassian.net/rest/api/3/user?accountId=5b10a2844c20165700ede21g"},"updated":"2021-01-18T23:45:00.000+0000","visibility":{"identifier":"Administrators","type":"role","value":"Administrators"}}
1
brew tap atlassian/tap
Then install the SDK using the atlassian/tap command:
1
brew install atlassian/tap/atlassian-plugin-sdk
[Next: Verify that you have set up the SDK correctly](https://developer.atlassian.com/display/DOCS/Install+the+Atlassian+SDK+on+a+Linux+or+Mac+system#step-3--verify-that-you-have-set-up-the-sdk-correctly)
Debian, Ubuntu Linux
On a Debian-based Linux system like Ubuntu, you can install the SDK using apt-get or aptitude:
First, set up the Atlassian SDK repositories:
1
sudo sh -c 'echo "deb https://packages.atlassian.com/debian/atlassian-sdk-deb/ stable contrib" >>/etc/apt/sources.list'
Download the public key using curl or wget:
1
wget https://packages.atlassian.com/api/gpg/key/public    
Add the public key to apt to verify the package signatures automatically:
1
sudo apt-key add public   
Then, run the install:
1
2
sudo apt-get update
sudo apt-get install atlassian-plugin-sdk
[Next: Verify that you have set up the SDK correctly](https://developer.atlassian.com/server/framework/atlassian-sdk/install-the-atlassian-sdk-on-a-linux-or-mac-system/#step-3--verify-that-you-have-set-up-the-sdk-correctly)
Red Hat Enterprise Linux, CentOS, Fedora (RPM)
To install on systems that use the Yum package manager:
Create the repo file in your /etc/yum.repos.d/ folder:
1
sudo vi /etc/yum.repos.d/artifactory.repo
Configure the repository details:
1
2
3
4
5
[Artifactory]
name=Artifactory
baseurl=https://packages.atlassian.com/yum/atlassian-sdk-rpm/
enabled=1
gpgcheck=0
Install the SDK:
1
2
3
sudo yum clean all
sudo yum updateinfo metadata
sudo yum install atlassian-plugin-sdk
As always,[Verify that you have set up the SDK correctly.](https://developer.atlassian.com/server/framework/atlassian-sdk/install-the-atlassian-sdk-on-a-linux-or-mac-system/#step-3--verify-that-you-have-set-up-the-sdk-correctly)
.tgz File
To install the latest version of SDK, do the following:
[Download a TGZ (GZipped tar file) of the SDK](https://marketplace.atlassian.com/download/plugins/atlassian-plugin-sdk-tgz)
Locate the downloaded SDK file. 
Extract the file to your local directory.
1
sudo tar -xvzf atlassian-plugin-sdk-4.0.tar.gz -C /opt
Rename the extracted folder to  atlassian-plugin-sdk .
1
sudo mv /opt/atlassian-plugin-sdk-4.0 /opt/atlassian-plugin-sdk 
If you are comfortable working with symbolic links, you can set up a symbolic link instead of renaming the directory.
[Next: Verify that you have set up the SDK correctly](https://developer.atlassian.com/display/DOCS/Install+the+Atlassian+SDK+on+a+Linux+or+Mac+system#step-3--verify-that-you-have-set-up-the-sdk-correctly)
Step 3: Verify that you have set up the SDK correctly
Open a terminal window and run the following command:
1
atlas-version
You should see something similar to:
1
2
3
4
5
6
7
8
9
10
11
12
13
14
ATLAS Version:    6.2.9
ATLAS Home:       /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec
ATLAS Scripts:    /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec/bin
ATLAS Maven Home: /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec/apache-maven-3.2.1
AMPS Version:     6.2.6
--------
Executing: /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec/apache-maven-3.2.1/bin/mvn --version -gs /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec/apache-maven-3.2.1/conf/settings.xml
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=256M; support was removed in 8.0
Apache Maven 3.2.1 (ea8b2b07643dbb1b84b6d16e1f08391b666bc1e9; 2014-02-15T04:37:52+10:00)
Maven home: /usr/local/Cellar/atlassian-plugin-sdk/6.2.4/libexec/apache-maven-3.2.1
Java version: 1.8.0_45, vendor: Oracle Corporation
Java home: /Library/Java/JavaVirtualMachines/jdk1.8.0_45.jdk/Contents/Home/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "mac os x", version: "10.11.6", arch: "x86_64", family: "mac"
Look for Maven home and note that you are running the version of Maven that is installed with the SDK.
Next step
You now have a local development environment configured for the Atlassian SDK and you're ready to build your first plugin!

atlas-create-jira-plugin
This command is going to build a JIRA plugin skeleton using maven. Some logs appear on the screen showing maven commands that are being run and the version of JIRA that is being used. 
You will be prompted to provide some information about your plugin. For the purposes of this tutorial respond to the prompts as follows:
1
2
3
4
Define value for groupId: : com.atlassian.tutorial
Define value for artifactId: : myPlugin
Define value for version: 1.0.0-SNAPSHOT: : 1.0.0-SNAPSHOT
Define value for package: com.atlassian.tutorial: : com.atlassian.tutorial.myPlugin
You will then be prompted to confirm your configuration. Verify the details to ensure they are correct, and then type Y once you are ready to proceed:
1
2
3
4
5
6
Confirm properties configuration:
groupId: com.atlassian.tutorial
artifactId: myPlugin
version: 1.0.0-SNAPSHOT
package: com.atlassian.tutorial.myPlugin
Y: : Y
The basic skeleton for your Atlassian JIRA plugin is created in a new myPlugin directory: 
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
.
├── LICENSE
├── README
├── pom.xml
└── src
    ├── main
    │   ├── java
    │   │   └── com
    │   │       └── atlassian
    │   │           └── tutorial
    │   │               └── myPlugin
    │   │                   ├── api
    │   │                   │   └── MyPluginComponent.java
    │   │                   └── impl
    │   │                       └── MyPluginComponentImpl.java
    │   └── resources
    │       ├── META-INF
    │       │   └── spring
    │       │       └── plugin-context.xml
    │       ├── atlassian-plugin.xml
    │       ├── css
    │       │   └── myPlugin.css
    │       ├── images
    │       │   ├── pluginIcon.png
    │       │   └── pluginLogo.png
    │       ├── myPlugin.properties
    │       └── js
    │           └── myPlugin.js
    └── test
        ├── java
        │   ├── it
        │   │   └── com
        │   │       └── atlassian
        │   │           └── tutorial
        │   │               └── myPlugin
        │   │                   └── MyComponentWiredTest.java
        │   └── ut
        │       └── com
        │           └── atlassian
        │               └── tutorial
        │                   └── myPlugin
        │                       └── MyComponentUnitTest.java
        └── resources
            └── atlassian-plugin.xml
Feel free to take a moment to explore the different files created by the Atlassian SDK before you continue. 
Step 2. Start up JIRA with your plugin installed
In this step, we'll use the atlas-run command to run the application (JIRA in this example) and install the plugin. Then we'll confirm that JIRA has started with the plugin created in Step 1 already installed.   
Change to the myPlugin directory and enter the following command: 
1
 atlas-run
This is going to use the information in the plugin skeleton you created earlier to download JIRA and all of the other plugins it needs, then start JIRA with your plugin installed.  
The first time you do this, it might take several minutes to complete.  
Once JIRA has started, you'll see something like this in the Command Prompt window:
1
2
3
4
5
6
[INFO] [talledLocalContainer] Aug 08, 2016 5:51:33 PM org.apache.catalina.startup.Catalina start
[INFO] [talledLocalContainer] INFO: Server startup in 234207 ms
[INFO] [talledLocalContainer] Tomcat 8.x started on port [2990]
[INFO] jira started successfully in 332s at http://DESKTOP-EF2CA9N:2990/jira
[INFO] Type Ctrl-D to shutdown gracefully
[INFO] Type Ctrl-C to exit

Open the pom.xml file in your favourite editor. 
Locate the <organization> element in the file. It should look something like this:
1
2
3
4
<organization>
    <name>Example Company</name>
    <url>http://www.example.com/</url>
</organization>
Update the element to include some personalized information, for example:
1
2
3
4
<organization>
    <name>Atlassian SDK Tutorial</name>
    <url>http://developer.atlassian.com/</url>
</organization>
Save and close the file.
Return to the **command prompt **window, and enter atlas-run and wait for JIRA to start back up.
Login if prompted
Open the Manage add-ons page in your browser using the path: [localhost:2990/jira/plugins/servlet/upm](http://localhost:2990/jira/plugins/servlet/upm)
Expand the myPlugin plugin to see your changes.
When you're finished, shutdown JIRA gracefully using Ctrl+D. 
Step 2. Add a custom menu to JIRA  
Open the /src/main/resources/atlassian-plugin.xml file from your** **myPlugin directory in your favourite text editor.  
The atlassian-plugin.xml file will look something like this: 
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
<atlassian-plugin key="${atlassian.plugin.key}" name="${project.name}" plugins-version="2">
    <plugin-info>
        <description>${project.description}</description>
        <version>${project.version}</version>
        <vendor name="${project.organization.name}" url="${project.organization.url}" />
        <param name="plugin-icon">images/pluginIcon.png</param>
        <param name="plugin-logo">images/pluginLogo.png</param>
    </plugin-info>
    <!-- add our i18n resource -->
    <resource type="i18n" name="i18n" location="myPlugin"/>
    <!-- add our web resources -->
    <web-resource key="myPlugin-resources" name="myPlugin Web Resources">
        <dependency>com.atlassian.auiplugin:ajs</dependency>
        <resource type="download" name="myPlugin.css" location="/css/myPlugin.css"/>
        <resource type="download" name="myPlugin.js" location="/js/myPlugin.js"/>
        <resource type="download" name="images/" location="/images"/>
        <context>myPlugin</context>
    </web-resource>
</atlassian-plugin>
Next, in **command prompt **make sure you're in the myPlugin folder and then run the following command:
1
atlas-create-jira-plugin-module
You'll be prompted to choose a plugin module from a list of possible module types (check out [Plugin Modules](https://developer.atlassian.com/server/framework/atlassian-sdk/plugin-modules) for more information).
Type 30 to select the Web Section plugin module type.
Now, you'll be prompted to answer a few configuration questions, answer as follows:
1
2
3
Enter Plugin Module Name My Web Section: : mySection
Enter Location (e.g. system.admin/mynewsection): my-item-link
Show Advanced Setup? (Y/y/N/n) N: : N
At the moment the location my-item-link doesn't exist, but we'll create that in the next step.
Next, you're prompted to enter another plugin module. Type Y to create another module. 
Type 25 to select the Web Item plugin module and then answer the configuration questions as follows:
1
2
3
4
Enter Plugin Module Name My Web Item: : myItem
Enter Section (e.g. system.admin/globalsettings): system.top.navigation.bar
Enter Link URL (e.g. /secure/CreateIssue!default.jspa): deleteMe
Show Advanced Setup? (Y/y/N/n) N: : N
When you are prompted to enter another Plugin Module, type N. 
The system will complete the creation of the modules and you'll receive a confirmation that the build was successful. 
Step 3. Customise the menu
Open the atlassian-plugin.xml file and you'll notice it has changed a little:
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
<?xml version="1.0" encoding="UTF-8"?>


<atlassian-plugin key="${atlassian.plugin.key}" name="${project.name}" plugins-version="2">
  <plugin-info>
    <description>${project.description}</description>
    <version>${project.version}</version>
    <vendor name="${project.organization.name}" url="${project.organization.url}"/>
    <param name="plugin-icon">images/pluginIcon.png</param>
    <param name="plugin-logo">images/pluginLogo.png</param>
  </plugin-info>
  <!-- add our i18n resource -->
  <resource type="i18n" name="i18n" location="myPlugin"/>
  <!-- add our web resources -->
  <web-resource key="myPlugin-resources" name="myPlugin Web Resources">
    <dependency>com.atlassian.auiplugin:ajs</dependency>
    <resource type="download" name="myPlugin.css" location="/css/myPlugin.css"/>
    <resource type="download" name="myPlugin.js" location="/js/myPlugin.js"/>
    <resource type="download" name="images/" location="/images"/>
    <context>myPlugin</context>
  </web-resource>
  <web-section name="mySection" i18n-name-key="my-section.name" key="my-section" location="my-item-link" 
weight="1000">
    <description key="my-section.description">The mySection Plugin</description>
    <label key="my-section.label"/>
  </web-section>
  <web-item name="myItem" i18n-name-key="my-item.name" key="my-item" section="system.top.navigation.bar" 
weight="1000">
    <description key="my-item.description">The myItem Plugin</description>
    <label key="my-item.label"></label>
    <link linkId="my-item-link">deleteMe</link>
  </web-item>
</atlassian-plugin>

<component-import 
  key="appProps" 
  interface="com.atlassian.sal.api.ApplicationProperties"/>

<plugin-info>
    <description>A macro which displays Google maps within a Confluence page.</description>
    <vendor name="Atlassian Software Systems Pty Ltd" url="http://www.atlassian.com/"/>
    <version>0.1</version>
    <param name="configure.url">/admin/plugins/gmaps/configurePlugin.action</param>
</plugin-info>

pip install timml --upgrade
To uninstall TimML type:

pip uninstall timml
Experimental and for radial flow only
import numpy as np
import matplotlib.pyplot as plt
import timml as tml
rw = 5
ml = tml.Model3D(kaq=10, z=np.arange(20, -1, -2), kzoverkh=50) w = tml.LargeDiameterWell(ml, Qw=100, layers=[0, 1, 2, 3, 4], rw=rw) rf = tml.Constant(ml, 100, 0, 20)
ml.solve()
Number of elements, Number of equations: 2 , 11
..
solution complete
xg = np.linspace(rw, 50, 100)
h = ml.headalongline(xg, 0)
for i in range(10):
    plt.plot(xg, h[i])
plt.xlim(0, 50)
plt.xticks(np.arange(0, 51, 5))
plt.grid()

qx = ml.disvec(rw, 0)[0]
print(qx * 2 * np.pi * rw)
print(np.sum(qx * 2 * np.pi * rw))
[-1.50511966e+01 -1.54865781e+01 -1.66133444e+01 -1.94936336e+01
 -3.32803095e+01 -6.18665346e-03 -2.60712180e-02  2.81040181e-02
  7.22067838e-03  1.38265742e-02]
-99.90816871499192
ml.head(rw, 0)
array([19.7515328 , 19.75153236, 19.75153185, 19.75153275, 19.75153281,
       19.76498845, 19.77043627, 19.77362338, 19.77547235, 19.7763392 ])
from scipy.special import k0
k0(5 / ml.aq.lab[1:])
array([2.06829668e-03, 6.74900159e-06, 3.32024764e-08, 2.57897091e-10,
       3.46416156e-12, 8.82738725e-14, 4.63575933e-15, 5.37054606e-16,
       1.44345016e-16])
ml.aq.eigvec
array([[ 1.00000000e-01,  4.41707654e-01,  4.25325404e-01,
        -3.98470231e-01,  3.61803399e-01, -3.16227766e-01,
         2.62865556e-01, -2.03030724e-01, -1.38196601e-01,
        -6.99596196e-02],
       [ 1.00000000e-01,  3.98470231e-01,  2.62865556e-01,
        -6.99596196e-02, -1.38196601e-01,  3.16227766e-01,
        -4.25325404e-01,  4.41707654e-01,  3.61803399e-01,
         2.03030724e-01],
       [ 1.00000000e-01,  3.16227766e-01, -3.10776816e-17,
         3.16227766e-01, -4.47213595e-01,  3.16227766e-01,
        -2.38891966e-16, -3.16227766e-01, -4.47213595e-01,
        -3.16227766e-01],
       [ 1.00000000e-01,  2.03030724e-01, -2.62865556e-01,
         4.41707654e-01, -1.38196601e-01, -3.16227766e-01,
         4.25325404e-01, -6.99596196e-02,  3.61803399e-01,
         3.98470231e-01],
       [ 1.00000000e-01,  6.99596196e-02, -4.25325404e-01,
         2.03030724e-01,  3.61803399e-01, -3.16227766e-01,
        -2.62865556e-01,  3.98470231e-01, -1.38196601e-01,
        -4.41707654e-01],
       [ 1.00000000e-01, -6.99596196e-02, -4.25325404e-01,
        -2.03030724e-01,  3.61803399e-01,  3.16227766e-01,
        -2.62865556e-01, -3.98470231e-01, -1.38196601e-01,
         4.41707654e-01],
       [ 1.00000000e-01, -2.03030724e-01, -2.62865556e-01,
        -4.41707654e-01, -1.38196601e-01,  3.16227766e-01,
         4.25325404e-01,  6.99596196e-02,  3.61803399e-01,
        -3.98470231e-01],
       [ 1.00000000e-01, -3.16227766e-01, -2.90992345e-16,
        -3.16227766e-01, -4.47213595e-01, -3.16227766e-01,
        -5.07992125e-17,  3.16227766e-01, -4.47213595e-01,
         3.16227766e-01],
       [ 1.00000000e-01, -3.98470231e-01,  2.62865556e-01,
         6.99596196e-02, -1.38196601e-01, -3.16227766e-01,
        -4.25325404e-01, -4.41707654e-01,  3.61803399e-01,
        -2.03030724e-01],
       [ 1.00000000e-01, -4.41707654e-01,  4.25325404e-01,
         3.98470231e-01,  3.61803399e-01,  3.16227766e-01,
         2.62865556e-01,  2.03030724e-01, -1.38196601e-01,
         6.99596196e-02]]

  curl -v https://mysite.atlassian.net --user me@example.com:ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7
/ NcKhKEbWghsh1bSAUXEO1552

![https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator]

![https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862] ![https://characterai.io/static/tti/c/b/c/4/2/4/cbc424ac-52f3-4984-9b35-7e1953f200e9/0.webp]

authentic token NGROK (God's Time Travel Corporation) --header
'2avvD0NhbrJRkbxHpTCTKBldaL5_4ywouQsYBpunfxgtzZGxT'

authorization key SCP Foundation
--header
'0xh723hfva83445na7fn342h'

curl --location 'https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242

curl --location 'https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}

curl --location 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/2020-07-23' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}

curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location 'https://informatics.netify.ai/api/v1/intelligence/cryptocurrency_node/flows' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

https://informatics.netify.ai/api/v2/lookup/applications?filter_starts_with=f&filter_application_categories=["4","24"]

curl --location -g 'https://informatics.netify.ai/api/v2/lookup/applications?page=1&settings_limit=5&filter_starts_with=f&filter_application_categories=[%224%22%2C%2224%22]&settings_show_default_logo=false' \ --header 'https://dashboard.stripe.com/': EG' / and  --header 'https://scp-wiki.wikidot.com/':
EG'
Sample flow metadata from core processor
...
"detected_protocol_name": "HTTPS",
"detected_application_name": "netify.whatsapp.business", "ssl": {
  "alpn": [
    "h2",
    "http/1.1"
  ],
  "alpn_server": [],
  "version": "0x0303",
  "cipher_suite": "0xc02b",
  "client_sni": "static.whatsapp.net",
  "server_cn": "*.whatsapp.net",
  "client_ja3": "d8c87b9bfde38897979e4124262...",
  "server_ja3": "6e15a5bf660856fa03186247ca4...",
  "issuer_dn": "C=US, O=DigiCert Inc, OU=www...",
  "subject_dn": "C=US, ST=California, L=Menlo..."
},

# /etc/netifyd/plugins.d/10-netify-proc-core.conf

[proc-core]
enable = yes
...
# /etc/netifyd/netify-proc-core.json
{
   "format": "json",
   "compressor": "none",
   "sinks": {
      "sink-socket": {
         "default": {
             "enable": true,
             "types": [ "stream-flows", "stream-stats" ]
          },
          "tcp": {
             "enable": true,
             "types": [ "stream-flows", "stream-stats" ]
          },
      },
      "sink-mqtt": {
         "flows": {
            "enable": false,
            "types": [ "stream-flows" ]
         },
         "stats": {
            "enable": false,
            "types": [ "stream-stats" ]
         }
      }
   }

https://manager.netify.ai/api/v1/assets/agents

curl --location 'https://manager.netify.ai/api/v1/assets/agents' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

curl --location 'https://manager.netify.ai/api/v1/assets/agents/CH-AM-BE-RS' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

curl --location 'https://informatics.netify.ai/api/v2/lookup/platforms/cloudflare'

curl --location 'https://informatics.netify.ai/api/v2/lookup/platforms'

curl --location 'https://informatics.netify.ai/api/v2/lookup/platforms'

curl --location 'https://informatics.netify.ai/api/v2/lookup/domains/twitter.com'

curl --location 'https://informatics.netify.ai/api/v2/lookup/signatures/categories' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' ...
 X-SHA256-Hash: 8cb030f2...
 X-SHA256-Applications-Hash: b01e4196e...

...
 "data_info": {
    "hash": "8cb030f2c4...",
    "applications_hash": "b01e4196e..."
 },

...
 X-SHA256-Hash: b01e4196e...

...
 "data_info": {
    "hash": "b01e4196e...",
    "entries": 16798
 }
curl --location 'https://informatics.netify.ai/api/v2/lookup/signatures/applications?settings_version=4.2.5&settings_format=normal' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v2/lookup/signatures/applications?settings_version=4.2.5&settings_format=normal

https://informatics.netify.ai/api/v1/intelligence/discovery/devices

curl --location 'https://informatics.netify.ai/api/v1/intelligence/discovery/devices' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

curl --location 'https://informatics.netify.ai/api/v1/intelligence/discovery/devices/ac:ed:5c:00:00:00' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard

curl --location 'https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard

curl --location 'https://informatics.netify.ai/api/v1/intelligence/discovery/devices/ac:ed:5c:00:00:00' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}

curl --location 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline

curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

https://informatics.netify.ai/api/v1/intelligence/ip_reputation/:date

curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/2020-07-23' \ --header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \ --data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

curl --location 'https://informatics.netify.ai/api/v2/lookup/applications/twitter'

https://informatics.netify.ai/api/v2/lookup/protocols?filter_starts_with=f&filter_protocol_categories=["2","17"]

curl --location 'https://informatics.netify.ai/api/v2/lookup/protocols?page=1&settings_limit=5'

https://informatics.netify.ai/api/v2/lookup/protocols/:id

curl --location 'https://informatics.netify.ai/api/v2/lookup/protocols/bittorrent'

https://informatics.netify.ai/api/v2/lookup/protocol_categories

curl --location 'https://informatics.netify.ai/api/v2/lookup/protocol_categories' \ --header 'https://scp-wiki.wikidot.com/'
/ and
--header 'https://dashboard.stripe.com/'
/ and
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)'

...
 X-SHA256-Hash: b01e4196e...

curl --location 'https://informatics.netify.ai/api/v2/lookup/signatures/applications?settings_version=4.2.5&settings_format=normal' \ --header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

SCPiNET 3.7.61
--------
Initiating backup servers...
Accessing SCP-XXXX...
WARNING: Hash sum check failed. Checking file integrity... Attempting to recover files...
XXXX.scp failed!
XXXX.scp.old success!
XXXX.log success!
XXXX.a.incident failed!
XXXX.b.incident failed!
XXXX.c.incident success!
XXXX.d.incident failed!

<meta name="viewport" content="width=device-width, initial-scale=1.0"/> (all pages) remove
<meta name="description" content="The SCP Foundation's 'top-secret' archives, declassified for your enjoyment."/> (a


We could not find some of the files imported by the .proto file. Specify import paths to those unresolved files using the options below. Details: unresolved import: notification/notification/common/notification_code.proto import file : {source_root}/notification/endpoint/presentation/service.proto import paths : {source_root}/
However, it works normally in lower versions.

Steps To Reproduce

Write file
notification/endpoint/presentation/service.proto

syntax = "proto3";

package notification.endpoint.presentation;

import "notification/endpoint/presentation/create_device.proto";

service NotificationEndpointService {
  // Command
  rpc CreateDevice(CreateDeviceRequest) returns (CreateDeviceResponse) {}
}
notification/endpoint/presentation/create_device.proto

syntax = "proto3";

package notification.endpoint.presentation;

message CreateDeviceRequest {
  string name = 1;
}

message CreateDeviceResponse {}
import '{source_root}/notification/endpoint/presentation/service.proto' file in postman

set '{source_root}' in postman's import paths


curl --location --globoff '{{[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user' \ --data ''
{
    "data": [
        {
            "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
            "username": "cgkjl@fjkdsf.co",
            "name": "jsdfgsdgfdgdfdfgs",
            "last_name": "fghfghgfhfggz",
            "created_at": "2022-06-02T12:40:43.632Z",
            "updated_at": "2022-06-02T12:40:43.632Z"
        },
        {
            "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
            "username": "cgkjl@fjkdsf.co",
            "name": "jsdfgsdgfdgdfdfgs",
            "last_name": "fghfghgfhfggz",
            "created_at": "2022-06-02T12:40:43.632Z",
            "updated_at": "2022-06-02T12:40:43.632Z"
        },
        {
            "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
            "username": "cgkjl@fjkdsf.co",
            "name": "jsdfgsdgfdgdfdfgs",
            "last_name": "fghfghgfhfggz",
            "created_at": "2022-06-02T12:40:43.632Z",
            "updated_at": "2022-06-02T12:40:43.632Z"
        }
    ],
    "detail": {
        "http_code": 200,
        "info": "The request has been successfully processed",
        "status": true
    }
}
curl --location --globoff '{{[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user/{{grateful345i@gmail.com}}' {
    "data": {
        "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
        "username": "cgkjl@fjkdsf.co",
        "name": "jsdfgsdgfdgdfdfgs",
        "last_name": "fghfghgfhfggz",
        "created_at": "2022-06-02T12:40:43.632Z",
        "updated_at": "2022-06-02T12:40:43.632Z"
    },
    "detail": {
        "http_code": 200,
        "info": "The request has been successfully processed",
        "status": true
    }
}
{

    "username": "grateful345i@gmail.com",
    "password": "2334"
}
curl --location --globoff '{{[[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user/login' \ --data-raw '{

    "username": "joseluis@cloudappi.net",
    "password": "2334"
}'
{
    "data": {
        "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICIwMVRMZXhRLTdaSHVRTzd5UkloZklqZ0FzbHBqLUptbFUzS1p6a0pTcjRNIn0.eyJleHAiOjE2NTQyMDk1ODIsImlhdCI6MTY1NDE3MzU4MiwianRpIjoiMTRkZmRjOTEtNGFhNC00NWZjLWI5YTgtNjdmZGRjMjVmZGEzIiwiaXNzIjoiaHR0cHM6Ly9rZXljbG9hay5jbG91ZGFwcGkubmV0L2F1dGgvcmVhbG1zL0FwaS1xdWFsaXR5IiwiYXVkIjpbInJlYWxtLW1hbmFnZW1lbnQiLCJhY2NvdW50Il0sInN1YiI6IjY2MjJjYWYxLWJiMmMtNDkwZS1iZTUxLTdkYThmZjI2ZDdjOSIsInR5cCI6IkJlYXJlciIsImF6cCI6ImFwaS1xdWFsaXR5LWJhY2tlbmQiLCJzZXNzaW9uX3N0YXRlIjoiZDljZWI0OGEtYmY5Yy00MTFjLTg4ZjYtNjJlZTIxMzNmZDk1IiwiYWNyIjoiMSIsInJlYWxtX2FjY2VzcyI6eyJyb2xlcyI6WyJkZWZhdWx0LXJvbGVzLWFwaS1xdWFsaXR5Il19LCJyZXNvdXJjZV9hY2Nlc3MiOnsicmVhbG0tbWFuYWdlbWVudCI6eyJyb2xlcyI6WyJ2aWV3LXJlYWxtIiwidmlldy1pZGVudGl0eS1wcm92aWRlcnMiLCJtYW5hZ2UtaWRlbnRpdHktcHJvdmlkZXJzIiwiaW1wZXJzb25hdGlvbiIsInJlYWxtLWFkbWluIiwiY3JlYXRlLWNsaWVudCIsIm1hbmFnZS11c2VycyIsInF1ZXJ5LXJlYWxtcyIsInZpZXctYXV0aG9yaXphdGlvbiIsInF1ZXJ5LWNsaWVudHMiLCJxdWVyeS11c2VycyIsIm1hbmFnZS1ldmVudHMiLCJtYW5hZ2UtcmVhbG0iLCJ2aWV3LWV2ZW50cyIsInZpZXctdXNlcnMiLCJ2aWV3LWNsaWVudHMiLCJtYW5hZ2UtYXV0aG9yaXphdGlvbiIsIm1hbmFnZS1jbGllbnRzIiwicXVlcnktZ3JvdXBzIl19LCJhcGktcXVhbGl0eS1iYWNrZW5kIjp7InJvbGVzIjpbImFkbWluIl19LCJhY2NvdW50Ijp7InJvbGVzIjpbIm1hbmFnZS1hY2NvdW50IiwibWFuYWdlLWFjY291bnQtbGlua3MiLCJ2aWV3LXByb2ZpbGUiXX19LCJzY29wZSI6ImVtYWlsIHJvbGVzIHByb2ZpbGUiLCJlbWFpbF92ZXJpZmllZCI6ZmFsc2UsIm9yZ2FuaXphdGlvbiI6W10sIm5hbWUiOiJqb3NlbHVpcyBnb21leiIsInByZWZlcnJlZF91c2VybmFtZSI6Impvc2VsdWlzQGNsb3VkYXBwaS5uZXQiLCJnaXZlbl9uYW1lIjoiam9zZWx1aXMiLCJmYW1pbHlfbmFtZSI6ImdvbWV6In0.ubaHr3HTe46mTMwtvWbgvmjKmko2VZIyvFyYFHQpvj3tqAaO88Wu2ePomNuGgvKev_uJL433hmElPPWDPURqppIuLfhHGwptsfRPNNYld87s8ZMWnLw4Me5oOPNm2Rw7GevmhlWzIGvG48zFrNHQz8gZer9bjPInOhEMp-DMwV9jlX3efY0R8Qa-iXrrtcRql23Ept1tODj07RftkDEBD_FWD39lsi3JSTwvKXKHbEc9GzWZ_6mS_A82C_JE1iTI1hA_2tKdlQ1jEYcxRP8jSDtl40fMkOYRt1kay6ZahMnl9DNmGleNIUjXLrxJRNnJva5bi_ZGM6mVjaVZea3eVQ",
        "expires_in": 36000,
        "refresh_expires_in": 1800,
        "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJiNWZlNTAxOC04YzBiLTQ2YzAtYTQyMS0zNTQyMjUyZWM4ZWUifQ.eyJleHAiOjE2NTQxNzUzODIsImlhdCI6MTY1NDE3MzU4MiwianRpIjoiZmYyNmQ0OTEtM2JmOS00ZDgzLTk5NjQtNDA3ZWI0NDNlZTkxIiwiaXNzIjoiaHR0cHM6Ly9rZXljbG9hay5jbG91ZGFwcGkubmV0L2F1dGgvcmVhbG1zL0FwaS1xdWFsaXR5IiwiYXVkIjoiaHR0cHM6Ly9rZXljbG9hay5jbG91ZGFwcGkubmV0L2F1dGgvcmVhbG1zL0FwaS1xdWFsaXR5Iiwic3ViIjoiNjYyMmNhZjEtYmIyYy00OTBlLWJlNTEtN2RhOGZmMjZkN2M5IiwidHlwIjoiUmVmcmVzaCIsImF6cCI6ImFwaS1xdWFsaXR5LWJhY2tlbmQiLCJzZXNzaW9uX3N0YXRlIjoiZDljZWI0OGEtYmY5Yy00MTFjLTg4ZjYtNjJlZTIxMzNmZDk1Iiwic2NvcGUiOiJlbWFpbCByb2xlcyBwcm9maWxlIn0.qUdcdVWz0IAg4Pr0GuKvxc0haNk3q16s7DjeROykwSI",
        "token_type": "Bearer",
        "not-before-policy": 0,
        "session_state": "d9ceb48a-bf9c-411c-88f6-62ee2133fd95",
        "scope": "email roles profile"
    },
    "detail": {
        "http_code": 200,
        "info": "The request has been successfully processed",
        "status": true
    }
}
curl --location --globoff '{{[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user' \ --data-raw '{
   
   "username":"ul@cloudappi.net",
   "emailVerified":true,
   "firstName":"dar",
   "lastName":"dar",
   "password": "2334"
   
}'
$ npm install openapi-to-postmanv2
If you want to use the converter in the CLI, install it globally with NPM:

$ npm i -g openapi-to-postmanv2
📖 Command Line Interface

The converter can be used as a CLI tool as well. The following command line options are available.

openapi2postmanv2 [options]

Options

-s <source>, --spec <source> Used to specify the OpenAPI specification (file path) which is to be converted

-o <destination>, --output <destination> Used to specify the destination file in which the collection is to be written

-p, --pretty Used to pretty print the collection object while writing to a file

-i, --interface-version Specifies the interface version of the converter to be used. Value can be 'v2' or 'v1'. Default is 'v2'.

-O, --options Used to supply options to the converter, for complete options details see here

-c, --options-config Used to supply options to the converter through config file, for complete options details see here

-t, --test Used to test the collection with an in-built sample specification

-v, --version Specifies the version of the converter

-h, --help Specifies all the options along with a few usage examples on the terminal

Usage

Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options $ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,includeAuthInfoInExample=false Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options via config file $ openapi2postmanv2 -s spec.yaml -o collection.json -p  -c ./examples/cli-options-config.json Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options (Also avoids any "<Error: Too many levels of nesting to fake this schema>" kind of errors present in converted collection) $ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,requestParametersResolution=Example,optimizeConversion=false,stackLimit=50 $ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,includeAuthInfoInExample=false Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options via config file $ openapi2postmanv2 -s spec.yaml -o collection.json -p  -c ./examples/cli-options-config.json Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options (Also avoids any "<Error: Too many levels of nesting to fake this schema>" kind of errors present in converted collection) $ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,requestParametersResolution=Example,optimizeConversion=false,stackLimit=50 Testing the converter
$ openapi2postmanv2 --test
🛠 Using the converter as a NodeJS module

In order to use the convert in your node application, you need to import the package using require.

var Converter = require('openapi-to-postmanv2')
The converter provides the following functions:

Convert

The convert function takes in your OpenAPI 3.0, 3.1 and Swagger 2.0 specification ( YAML / JSON ) and converts it to a Postman collection.

Signature: convert (data, options, callback);

data:

{ type: 'file', data: 'filepath' }
OR
{ type: 'string', data: '<entire OpenAPI string - JSON or YAML>' } OR
{ type: 'json', data: OpenAPI-JS-object }
options:

{
  schemaFaker: true,
  requestNameSource: 'fallback',
  indentCharacter: ' '
}
/*
All three properties are optional. Check the options section below for possible values for each option. */
Note: All possible values of options and their usage can be found over here: OPTIONS.md

callback:

function (err, result) {
  /*
  result = {
    result: true,
    output: [
      {
        type: 'collection',
        data: {..collection object..}
      }
    ]
  }
  */
}
Options

Check out complete list of options and their usage at OPTIONS.md

ConversionResult

result - Flag responsible for providing a status whether the conversion was successful or not.

reason - Provides the reason for an unsuccessful conversion, defined only if result if false.

output - Contains an array of Postman objects, each one with a type and data. The only type currently supported is collection.

Sample Usage

const fs = require('fs'),
  Converter = require('openapi-to-postmanv2'),
  openapiData = fs.readFileSync('sample-spec.yaml', {encoding: 'UTF8'});

Converter.convert({ type: 'string', data: openapiData },
  {}, (err, conversionResult) => {
    if (!conversionResult.result) {
      console.log('Could not convert', conversionResult.reason);
    }
    else {
      console.log('The collection object is: ', conversionResult.output[0].data);
    }
  }
);
Validate Function

The validate function is meant to ensure that the data that is being passed to the convert function is a valid JSON object or a valid (YAML/JSON) string.

The validate function is synchronous and returns a status object which conforms to the following schema

Validation object schema

{
  type: 'object',
  properties: {
    result: { type: 'boolean'},
    reason: { type: 'string' }
  },
  required: ['result']
}
  text/plain; charset=utf-8
  application/json
  application/vnd.github+json
  application/vnd.github.v3+json
  application/vnd.github.v3.raw+json
  application/vnd.github.v3.text+json
  application/vnd.github.v3.html+json
  application/vnd.github.v3.full+json
  application/vnd.github.v3.diff
  application/vnd.github.v3.patch{
   "field": [ 1, 2, 3 ]
}{
  "type": "oauth2",
  "flows": {
    "implicit": {
      "authorizationUrl": "https://example.com/api/oauth/dialog",
      "scopes": {
        "write:pets": "modify pets in your account",
        "read:pets": "read your pets"
      }
    },
    "authorizationCode": {
      "authorizationUrl": "https://example.com/api/oauth/dialog",
      "tokenUrl": "https://example.com/api/oauth/token",
      "scopes": {
        "write:pets": "modify pets in your account",
        "read:pets": "read your pets"
      }
    }
  }
}
type: oauth2
flows:
  implicit:
    authorizationUrl: https://example.com/api/oauth/dialog
    scopes:
      write:pets: modify pets in your account
      read:pets: read your pets
  authorizationCode:
    authorizationUrl: https://example.com/api/oauth/dialog
    tokenUrl: https://example.com/api/oauth/token
    scopes:
      write:pets: modify pets in your account
      read:pets: read your pets
{
  "api_key": []
}
api_key: []
OAuth2 Security Requirement

{
  "petstore_auth": [
    "write:pets",
    "read:pets"
  ]
}
petstore_auth:
- write:pets
- read:pets{ "get": { "description": "Returns pets based on ID", "summary": "Find pets by ID", "operationId": "getPetsById", "responses": { "200": { "description": "pet response", "content": { "*/*": { "schema": { "type": "array", "items": { "$ref": "#/components/schemas/Pet" } } } } }, "default": { "description": "error payload", "content": { "text/html": { "schema": { "$ref": "#/components/schemas/ErrorModel" } } } } } }, "parameters": [ { "name": "id", "in": "path", "description": "ID of pet to use", "required": true, "schema": { "type": "array", "items": { "type": "string" } }, "style": "simple" } ] }
get:
  description: Returns pets based on ID summary: Find pets by ID operationId: getPetsById responses: '200': description: pet response content: '*/*' : schema: type: array items: $ref: '#/components/schemas/Pet' default: description: error payload content: 'text/html': schema: $ref: '#/components/schemas/ErrorModel' parameters:
- name: id in: path description: ID of pet to use required: true schema: type: array style: simple items: type: string  Operation Object

Describes a single API operation on a path.

Fixed Fields

Field Name	Type	Description
tags	[string]	A list of tags for API documentation control. Tags can be used for logical grouping of operations by resources or any other qualifier. summary	string	A short summary of what the operation does. description	string	A verbose explanation of the operation behavior. CommonMark syntax MAY be used for rich text representation. externalDocs	External Documentation Object	Additional external documentation for this operation. operationId	string	Unique string used to identify the operation. The id MUST be unique among all operations described in the API. The operationId value is case-sensitive. Tools and libraries MAY use the operationId to uniquely identify an operation, therefore, it is RECOMMENDED to follow common programming naming conventions. parameters	[Parameter Object | Reference Object]	A list of parameters that are applicable for this operation. If a parameter is already defined at the Path Item, the new definition will override it but can never remove it. The list MUST NOT include duplicated parameters. A unique parameter is defined by a combination of a name and location. The list can use the Reference Object to link to parameters that are defined at the OpenAPI Object's components/parameters. requestBody	Request Body Object | Reference Object	The request body applicable for this operation. The requestBody is only supported in HTTP methods where the HTTP 1.1 specification RFC7231 has explicitly defined semantics for request bodies. In other cases where the HTTP spec is vague, requestBody SHALL be ignored by consumers. responses	Responses Object	REQUIRED. The list of possible responses as they are returned from executing this operation. callbacks	Map[string, Callback Object | Reference Object]	A map of possible out-of band callbacks related to the parent operation. The key is a unique identifier for the Callback Object. Each value in the map is a Callback Object that describes a request that may be initiated by the API provider and the expected responses. The key value used to identify the callback object is an expression, evaluated at runtime, that identifies a URL to use for the callback operation. deprecated	boolean	Declares this operation to be deprecated. Consumers SHOULD refrain from usage of the declared operation. Default value is false. security	[Security Requirement Object]	A declaration of which security mechanisms can be used for this operation. The list of values includes alternative security requirement objects that can be used. Only one of the security requirement objects need to be satisfied to authorize a request. This definition overrides any declared top-level security. To remove a top-level security declaration, an empty array can be used. servers	[Server Object]	An alternative server array to service this operation. If an alternative server object is specified at the Path Item Object or Root level, it will be overridden by this value. This object MAY be extended with Specification Extensions.

Operation Object Example

{
  "tags": [
    "pet"
  ],
  "summary": "Updates a pet in the store with form data",
  "operationId": "updatePetWithForm",
  "parameters": [
    {
      "name": "petId",
      "in": "path",
      "description": "ID of pet that needs to be updated",
      "required": true,
      "schema": {
        "type": "string"
      }
    }
  ],
  "requestBody": {
    "content": {
      "application/x-www-form-urlencoded": {
        "schema": {
          "type": "object",
           "properties": {
              "name": {
                "description": "Updated name of the pet",
                "type": "string"
              },
              "status": {
                "description": "Updated status of the pet",
                "type": "string"
             }
           },
        "required": ["status"]
        }
      }
    }
  },
  "responses": {
    "200": {
      "description": "Pet updated.",
      "content": {
        "application/json": {},
        "application/xml": {}
      }
    },
    "405": {
      "description": "Method Not Allowed",
      "content": {
        "application/json": {},
        "application/xml": {}
      }
    }
  },
  "security": [
    {
      "petstore_auth": [
        "write:pets",
        "read:pets"
      ]
    }
  ]
}
tags:
- pet summary: Updates a pet in the store with form data operationId: updatePetWithForm
parameters:
- name: petId in: path description: ID of pet that needs to be updated required: true schema: type: string requestBody:
  content: 'application/x-www-form-urlencoded': schema: properties: name: description: Updated name of the pet type: string status: description: Updated status of the pet type: string required: - status responses:
  '200': description: Pet updated. content: 'application/json': {} 'application/xml': {} '405': description: Method Not Allowed content: 'application/json': {} 'application/xml': {} security:
- petstore_auth:
  - write:pets
  - read:pets {
  "name": "Apache 2.0",
  "url": "https://www.apache.org/licenses/LICENSE-2.0.html"
}name: Apache 2.0
url: https://www.apache.org/licenses/LICENSE-2.0.html{
  "url": "https://development.gigantic-server.com/v1",
  "description": "Development server"
}
url: https://development.gigantic-server.com/v1
description: Development server
The following shows how multiple servers can be described, for example, at the OpenAPI Object's servers:

{
  "servers": [
    {
      "url": "https://development.gigantic-server.com/v1",
      "description": "Development server"
    },
    {
      "url": "https://staging.gigantic-server.com/v1",
      "description": "Staging server"
    },
    {
      "url": "https://api.gigantic-server.com/v1",
      "description": "Production server"
    }
  ]
}
servers:
- url: https://development.gigantic-server.com/v1 description: Development server
- url: https://staging.gigantic-server.com/v1 description: Staging server
- url: https://api.gigantic-server.com/v1 description: Production server The following shows how variables can be used for a server configuration:

{
  "servers": [
    {
      "url": "https://{username}.gigantic-server.com:{port}/{basePath}",
      "description": "The production API server",
      "variables": {
        "username": {
          "default": "demo",
          "description": "this value is assigned by the service provider, in this example `gigantic-server.com`"
        },
        "port": {
          "enum": [
            "8443",
            "443"
          ],
          "default": "8443"
        },
        "basePath": {
          "default": "v2"
        }
      }
    }
  ]
}
servers:
- url: https://{username}.gigantic-server.com:{port}/{basePath} description: The production API server variables: username: # note! no enum here means it is an open value default: demo description: this value is assigned by the service provider, in this example `gigantic-server.com` port: enum: - '8443' - '443' default: '8443' basePath: # open meaning there is the opportunity to use special base paths as assigned by the provider, default is `v2` default: v2 EADME

License
CommonMark

CommonMark is a rationalized version of Markdown syntax, with a spec and BSD-licensed reference implementations in C and JavaScript.

Try it now!

For more details, see https://commonmark.org.

This repository contains the spec itself, along with tools for running tests against the spec, and for creating HTML and PDF versions of the spec.

The reference implementations live in separate repositories:

https://github.com/commonmark/cmark (C)
https://github.com/commonmark/commonmark.js (JavaScript) There is a list of third-party libraries in a dozen different languages here.

Running tests against the spec

The spec contains over 500 embedded examples which serve as conformance tests. To run the tests using an executable $PROG:

python3 test/spec_tests.py --program $PROG
If you want to extract the raw test data from the spec without actually running the tests, you can do:

python3 test/spec_tests.py --dump-tests
and you'll get all the tests in JSON format.

JavaScript developers may find it more convenient to use the commonmark-spec npm package, which is published from this repository. It exports an array tests of JSON objects with the format

{
  "markdown": "Foo\nBar\n---\n",
  "html": "<h2>Foo\nBar</h2>\n",
  "section": "Setext headings",
  "number": 65
}
The spec

The source of the spec is spec.txt. This is basically a Markdown file, with code examples written in a shorthand form:

```````````````````````````````` example
Markdown source
.
expected HTML output
````````````````````````````````

> these are two

> blockquotes

> this is a single
>
> blockquote with two paragraphs

pm.variables.has(variableName:String):function → Boolean Get the value of the Postman variable with the specified name: pm.variables.get(variableName:String):function → * Set a local variable with the specified name and value: pm.variables.set(variableName:String, variableValue:*):function Return the resolved value of a dynamic variable inside a script using the syntax {{$variableName}}: pm.variables.replaceIn(variableName:String):function: → * For example:

const stringWithVars = pm.variables.replaceIn("Hi, my name is {{$randomFirstName}}"); console.log(stringWithVars);
Return an object containing all variables with their values in the current scope. Based on the order of precedence, this will contain variables from multiple scopes. pm.variables.toObject():function → Object
postman.setNextRequest(requestName:String):Function Run the specified request after this one (the request ID returned by pm.info.requestId): postman.setNextRequest(requestId:String):Function
For example:

//script in another request calls:
//pm.environment.set('next', pm.info.requestId)
postman.setNextRequest(pm.environment.get('next')); Scripting Postman Visualizations

Use pm.visualizer.set to specify a template to display response data in the Postman Visualizer.

pm.visualizer.set(layout:String, data:Object, options:Object):Function layout required
Handlebars HTML template string
data optional
JSON object that binds to the template and you can access it inside the template string options optional
Options object for Handlebars.compile()
Example usage:

var template = `<p>{{res.info}}</p>`;
pm.visualizer.set(template, {
    res: pm.response.json()
});
Building response data into Postman Visualizations

Use pm.getData to retrieve response data inside a Postman Visualizer template string.

pm.getData(callback):Function
The callback function accepts two parameters:

error
Any error detail
data
Data passed to the template by pm.visualizer.set
Example usage:

pm.getData(function (error, data) {
  var value = data.res.info;
});
Writing test assertions

pm.test(testName:String, specFunction:Function):Function You can use pm.test to write test specifications inside either the Pre-request or Tests scripts. Tests include a name and assertion—Postman will output test results as part of the response.

The pm.test method returns the pm object, making the call chainable. The following sample test checks that a response is valid to proceed.

pm.test("response should be okay to process", function () {
  pm.response.to.not.be.error;
  pm.response.to.have.jsonBody('');
  pm.response.to.not.have.jsonBody('error');
});
An optional done callback can be passed to pm.test, to test asynchronous functions.

pm.test('async test', function (done) {
  setTimeout(() => {
    pm.expect(pm.response.code).to.equal(200);
    done();
  }, 1500);
});
Get the total number of tests executed from a specific location in code: pm.test.index():Function → Number
The pm.expect method allows you to write assertions on your response data, using ChaiJS expect BDD syntax.

pm.expect(assertion:*):Function → Assertion
You can also use pm.response.to.have.* and pm.response.to.be.* to build your assertions.

See Test examples for more assertions.

Using external libraries

require(moduleName:String):function → *
The require method allows you to use the 

> npm install postman-collection --save
Getting Started
In this example snippet we will get started by loading a collection from a file and output the same in console.

var fs = require('fs'), // needed to read JSON file from disk
	Collection = require('postman-collection').Collection,
	myCollection;

// Load a collection to memory from a JSON file on disk (say, sample-collection.json) myCollection = new Collection(JSON.parse(fs.readFileSync('sample-collection.json').toString()));

// log items at root level of the collection
console.log(myCollection.toJSON());
# Create a folder
$ mkdir actions-runner && cd actions-runner
# Download the latest runner package
$ curl -o actions-runner-linux-arm-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-linux-arm-2.314.1.tar.gz # Optional: Validate the hash
$ echo "a653dd46dafd47c9a3a6637a18161a1445ac6b9c3f6d6b0305be9e1ee65769af  actions-runner-linux-arm-2.314.1.tar.gz" | shasum -a 256 -c # Extract the installer
$ tar xzf ./actions-runner-linux-arm-2.314.1.tar.gz Configure
# Create the runner and start the configuration experience $ ./config.sh --url https://github.com/grateful345/AGENCY-WEBHOOK --token BHAHZGAPZ7TETPSETRUTYETF7TSAQ # Last step, run it!
$ ./run.sh
Using your self-hosted runner
# Use this YAML in your workflow file for each job runs-on: self-hosted
folder permissions and long path restrictions on Windows.

# Create a folder under the drive root
$ mkdir actions-runner; cd actions-runner
# Download the latest runner package
$ Invoke-WebRequest -Uri https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-win-arm64-2.314.1.zip -OutFile actions-runner-win-arm64-2.314.1.zip # Optional: Validate the hash
$ if((Get-FileHash -Path actions-runner-win-arm64-2.314.1.zip -Algorithm SHA256).Hash.ToUpper() -ne 'acc807696d1dcad6fb45f6038f884185c54c48127445c365e86d03adb164a9e2'.ToUpper()){ throw 'Computed checksum did not match' } # Extract the installer
$ Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$PWD/actions-runner-win-arm64-2.314.1.zip", "$PWD") Configure
# Create the runner and start the configuration experience $ ./config.cmd --url https://github.com/grateful345/AGENCY-WEBHOOK --token BHAHZGAPZ7TETPSETRUTYETF7TSAQ # Run it!
$ ./run.cmd
Using your self-hosted runner
# Use this YAML in your workflow file for each job runs-on: self-hosted
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/keys
# Create a folder
$ mkdir actions-runner && cd actions-runner
# Download the latest runner package
$ curl -o actions-runner-osx-arm64-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-osx-arm64-2.314.1.tar.gz # Optional: Validate the hash
$ echo "e34dab0b4707ad9a9db75f5edf47a804e293af853967a5e0e3b29c8c65f3a004  actions-runner-osx-arm64-2.314.1.tar.gz" | shasum -a 256 -c # Extract the installer
$ tar xzf ./actions-runner-osx-arm64-2.314.1.tar.gz Configure
# Create the runner and start the configuration experience $ ./config.sh --url https://github.com/grateful345/AGENCY-WEBHOOK --token BHAHZGAPZ7TETPSETRUTYETF7TSAQ # Last step, run it!
$ ./run.sh
Using your self-hosted runner
# Use this YAML in your workflow file for each job runs-on: self-hosted

{
  "type": "array",
  "items": {
    "title": "Deploy Key",
    "description": "An SSH key granting access to a single repository.",
    "type": "object",
    "properties": {
      "id": {
        "type": "integer"
      },
      "key": {
        "type": "string"
      },
      "url": {
        "type": "string"
      },
      "title": {
        "type": "string"
      },
      "verified": {
        "type": "boolean"
      },
      "created_at": {
        "type": "string"
      },
      "read_only": {
        "type": "boolean"
      },
      "added_by": {
        "type": [
          "string",
          "null"
        ]
      },
      "last_used": {
        "type": [
          "string",
          "null"
        ]
      }
    },
    "required": [
      "id",
      "key",
      "url",
      "title",
      "verified",
      "created_at",
      "read_only"
    ]
  }
}

curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/keys \
  -d '{"title":"octocat@octomac","key":"ssh-rsa AAA...","read_only":true}'

{
  "title": "Deploy Key",
  "description": "An SSH key granting access to a single repository.",
  "type": "object",
  "properties": {
    "id": {
      "type": "integer"
    },
    "key": {
      "type": "string"
    },
    "url": {
      "type": "string"
    },
    "title": {
      "type": "string"
    },
    "verified": {
      "type": "boolean"
    },
    "created_at": {
      "type": "string"
    },
    "read_only": {
      "type": "boolean"
    },
    "added_by": {
      "type": [
        "string",
        "null"
      ]
    },
    "last_used": {
      "type": [
        "string",
        "null"
      ]
    }
  },
  "required": [
    "id",
    "key",
    "url",
    "title",
    "verified",
    "created_at",
    "read_only"
  ]
}

curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/keys/KEY_ID

{
    "image": "mcr.microsoft.com/devcontainers/base:ubuntu"
}
However, [Dockerfiles](https://docs.docker.com/engine/reference/builder/) are a great way to extend images, add additional native OS packages, or make minor edits to the OS image. You can reuse any Dockerfile, but let’s walk through how to create one from scratch.

First, add a file named Dockerfile next to your devcontainer.json. For example:

FROM mcr.microsoft.com/devcontainers/base:ubuntu
# Install the xz-utils package
RUN apt-get update && apt-get install -y xz-utils
Next, remove the image property from devcontainer.json (if it exists) and add the build and dockerfile properties instead:

{
    "build": {
        // Path is relative to the devcontainer.json file.
        "dockerfile": "Dockerfile"
    }
}

YAML
name: Comment when opened
on:
  issues:
    types:
      - opened jobs:
  comment:
    runs-on: ubuntu-latest steps: - run: gh issue comment $ISSUE --body "Thank you for opening this issue!" env: GH_TOKEN: ${{ BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }} ISSUE: ${{ github.event.issue.html_url }} You can also execute API calls through GitHub CLI. For example, this workflow first uses the gh api subcommand to query the GraphQL API and parse the result. Then it stores the result in an environment variable that it can access in a later step. In the second step, it uses the gh issue create subcommand to create an issue containing the information from the first step.

YAML
name: Report remaining open issues
on: 
  schedule: 
    # Daily at 8:20 UTC
    - cron: '20 8 * * *'
jobs:
  track_pr:
    runs-on: ubuntu-latest
    steps:
      - run: | numOpenIssues="$(gh api graphql -F owner=$OWNER -F name=$REPO -f query=' query($name: String!, $owner: String!) { repository(owner: $Grateful345, name: $keith_Bieszczat) { issues(states:OPEN){ totalCount } } } ' --jq '.data.repository.issues.totalCount')"

          echo 'NUM_OPEN_ISSUES='$numOpenIssues >> $GITHUB_ENV
        env:
          GH_TOKEN: ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}
          OWNER: ${{ github.repository_owner }}
          REPO: ${{ Agency Webhook }}
      - run: |
          gh issue create --title "Issue report" --body "$NUM_OPEN_ISSUES issues remaining" --repo $GITHUB_REPOSITORY
        env:
          GH_TOKEN: ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}

name: Open new issue
on: workflow_dispatch

jobs:
  open-issue:
    runs-on: ubuntu-latest permissions: contents: read issues: write steps: - run: | gh issue --repo ${{ Agency Webhook }} \ create --title "Issue title" --body "Issue body" env: GH_TOKEN: ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }} [Example 2: calling the REST API](https://docs.github.com/en/actions/security-guides/automatic-token-authentication#example-2-calling-the-rest-api)

You can use the GITHUB_TOKEN to make authenticated API calls. This example workflow creates an issue using the GitHub REST API:

name: Create issue on commit

on: [ push ]

jobs:
  create_issue:
    runs-on: ubuntu-latest
    permissions:
      issues: write
    steps:
      - name: Create issue using REST API run: | curl --request POST \ --url https://api.github.com/repos/${{ github.repository }}/issues \ --header 'authorization: Bearer ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}' \ --header 'content-type: application/json' \ --data '{ "title": "Automated issue for commit: ${{ github.sha }}", "body": "This issue was automatically created by the GitHub Action workflow **${{ github.workflow }}**. \n\n The commit hash was: _${{ github.sha }}_." }' \ --fail

curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  "https://api.github.com/user/packages?package_type=container"
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/user/docker/conflicts
curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID/restore

curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions
  curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/restore
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  "https://api.github.com/orgs/ORG/packages?package_type=container"
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  curl -L \
  -X PATCH \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/applications/Iv1.8a61f9b3a7aba766/token \
  -d '{"access_token":"e72e16c7e42f292c6912e7710c838347ae178b4a"}'https://api.github.com/orgs/ORG/docker/conflicts curl --request GET \
--url "https://api.github.com/octocat" \
--header "Authorization: ghu_16C7e42F292c6912E7710c838347Ae178B4a", \ --header "X-GitHub-Api-Version: 2022-11-28"
Note
curl --request POST \
--url "https://api.github.com/applications/YOUR_CLIENT_ID/token" \ --user "YOUR_CLIENT_ID:YOUR_CLIENT_SECRET" \
--header "Accept: application/vnd.github+json" \
--header "X-GitHub-Api-Version: 2022-11-28" \
--data '{
  "access_token": "e72e16c7e42f292c6912e7710c838347ae178b4a"
}'
kubectl get SampleDB                   # find configured databases

kubectl edit SampleDB/example-database # manually change some settings sudo snap install multipass
Use Multipass to launch an Ubuntu VM with the charm-dev blueprint:

multipass launch --cpus 4 --memory 8G --disk 30G --name tutorial-vm charm-dev  Open a shell into the VM:

multipass shell tutorial-vm
Verify that you have Juju and two localhost clouds:

juju clouds
Bootstrap a Juju controller into the MicroK8s cloud:

juju bootstrap microk8s tutorial-controller
Add a workspace, or 'model':

juju add-model tutorial-model
Deploy, configure, and integrate a few things

Deploy Mattermost:

juju deploy mattermost-k8s
See more: Charmhub | mattermost-k8s
Deploy PostgreSQL:

juju deploy postgresql-k8s --channel 14/stable --trust See more: Charmhub | postgresql-k8s
Enable security in your PostgreSQL deployment:

juju deploy tls-certificates-operator
juju config tls-certificates-operator generate-self-signed-certificates="true" ca-common-name="Test CA" juju integrate postgresql-k8s tls-certificates-operator Integrate Mattermost with PostgreSQL:

juju integrate mattermost-k8s postgresql-k8s:db
Watch your deployment come to life:

juju status --watch 1s
(Press Ctrl-C to quit. Drop the --watch 1s flag to get the status statically. Use the --relations flag to view more information about your integrations.)

Test your deployment

When everything is in active or idle status, note the IP address and port of Mattermost and pass them to curl:

curl <IP address>:<port>/api/v4/system/ping
You should see the output below:

{"AndroidLatestVersion":"","AndroidMinVersion":"","IosLatestVersion":"","IosMinVersion":"","status":"OK"} Congratulations!

You now have a Kubernetes deployment consisting of a Mattermost backed by PosgreSQL wit

![https://characterai.io/static/tti/c/b/c/4/2/4/cbc424ac-52f3-4984-9b35-7e1953f200e9/0.webp]

authentic token NGROK (God's Time Travel Corporation)
--header
'2avvD0NhbrJRkbxHpTCTKBldaL5_4ywouQsYBpunfxgtzZGxT'

authorization key SCP Foundation
--header
'0xh723hfva83445na7fn342h'

curl --location 'https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242

curl --location 'https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}

curl --location 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/2020-07-23' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}

curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location 'https://informatics.netify.ai/api/v1/intelligence/cryptocurrency_node/flows' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

https://informatics.netify.ai/api/v2/lookup/applications?filter_starts_with=f&filter_application_categories=["4","24"]

curl --location -g 'https://informatics.netify.ai/api/v2/lookup/applications?page=1&settings_limit=5&filter_starts_with=f&filter_application_categories=[%224%22%2C%2224%22]&settings_show_default_logo=false' \
--header 'https://dashboard.stripe.com/': EG' / and 
--header 'https://scp-wiki.wikidot.com/':
EG'
Sample flow metadata from core processor
...
"detected_protocol_name": "HTTPS",
"detected_application_name": "netify.whatsapp.business",
"ssl": {
  "alpn": [
    "h2",
    "http/1.1"
  ],
  "alpn_server": [],
  "version": "0x0303",
  "cipher_suite": "0xc02b",
  "client_sni": "static.whatsapp.net",
  "server_cn": "*.whatsapp.net",
  "client_ja3": "d8c87b9bfde38897979e4124262...",
  "server_ja3": "6e15a5bf660856fa03186247ca4...",
  "issuer_dn": "C=US, O=DigiCert Inc, OU=www...",
  "subject_dn": "C=US, ST=California, L=Menlo..."
},

# /etc/netifyd/plugins.d/10-netify-proc-core.conf

[proc-core]
enable = yes
...
# /etc/netifyd/netify-proc-core.json
{
   "format": "json",
   "compressor": "none",
   "sinks": {
      "sink-socket": {
         "default": {
             "enable": true,
             "types": [ "stream-flows", "stream-stats" ]
          },
          "tcp": {
             "enable": true,
             "types": [ "stream-flows", "stream-stats" ]
          },
      },
      "sink-mqtt": {
         "flows": {
            "enable": false,
            "types": [ "stream-flows" ]
         },
         "stats": {
            "enable": false,
            "types": [ "stream-stats" ]
         }
      }
   }

https://manager.netify.ai/api/v1/assets/agents

curl --location 'https://manager.netify.ai/api/v1/assets/agents' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

curl --location 'https://manager.netify.ai/api/v1/assets/agents/CH-AM-BE-RS' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

curl --location 'https://informatics.netify.ai/api/v2/lookup/platforms/cloudflare'

curl --location 'https://informatics.netify.ai/api/v2/lookup/platforms'

curl --location 'https://informatics.netify.ai/api/v2/lookup/platforms'

curl --location 'https://informatics.netify.ai/api/v2/lookup/domains/twitter.com'

curl --location 'https://informatics.netify.ai/api/v2/lookup/signatures/categories' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'
...
 X-SHA256-Hash: 8cb030f2...
 X-SHA256-Applications-Hash: b01e4196e...

...
 "data_info": {
    "hash": "8cb030f2c4...",
    "applications_hash": "b01e4196e..."
 },

...
 X-SHA256-Hash: b01e4196e...

...
 "data_info": {
    "hash": "b01e4196e...",
    "entries": 16798
 }
curl --location 'https://informatics.netify.ai/api/v2/lookup/signatures/applications?settings_version=4.2.5&settings_format=normal' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v2/lookup/signatures/applications?settings_version=4.2.5&settings_format=normal

https://informatics.netify.ai/api/v1/intelligence/discovery/devices

curl --location 'https://informatics.netify.ai/api/v1/intelligence/discovery/devices' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

curl --location 'https://informatics.netify.ai/api/v1/intelligence/discovery/devices/ac:ed:5c:00:00:00' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard

curl --location 'https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard

curl --location 'https://informatics.netify.ai/api/v1/intelligence/discovery/devices/ac:ed:5c:00:00:00' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}

curl --location 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline

curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

https://informatics.netify.ai/api/v1/intelligence/ip_reputation/:date

curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/2020-07-23' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

curl --location 'https://informatics.netify.ai/api/v2/lookup/applications/twitter'

https://informatics.netify.ai/api/v2/lookup/protocols?filter_starts_with=f&filter_protocol_categories=["2","17"]

curl --location 'https://informatics.netify.ai/api/v2/lookup/protocols?page=1&settings_limit=5'

https://informatics.netify.ai/api/v2/lookup/protocols/:id

curl --location 'https://informatics.netify.ai/api/v2/lookup/protocols/bittorrent'

https://informatics.netify.ai/api/v2/lookup/protocol_categories

curl --location 'https://informatics.netify.ai/api/v2/lookup/protocol_categories' \
--header 'https://scp-wiki.wikidot.com/'
/ and
--header 'https://dashboard.stripe.com/'
/ and
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)'

...
 X-SHA256-Hash: b01e4196e...

curl --location 'https://informatics.netify.ai/api/v2/lookup/signatures/applications?settings_version=4.2.5&settings_format=normal' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

SCPiNET 3.7.61
--------
Initiating backup servers...
Accessing SCP-XXXX...
WARNING: Hash sum check failed. Checking file integrity...
Attempting to recover files...
XXXX.scp failed!
XXXX.scp.old success!
XXXX.log success!
XXXX.a.incident failed!
XXXX.b.incident failed!
XXXX.c.incident success!
XXXX.d.incident failed!

<meta name="viewport" content="width=device-width, initial-scale=1.0"/> (all pages)
remove
<meta name="description" content="The SCP Foundation's 'top-secret' archives, declassified for your enjoyment."/> (a


We could not find some of the files imported by the .proto file. Specify import paths to those unresolved files using the options below.
Details: unresolved import: notification/notification/common/notification_code.proto
import file : {source_root}/notification/endpoint/presentation/service.proto
import paths : {source_root}/
However, it works normally in lower versions.

Steps To Reproduce

Write file
notification/endpoint/presentation/service.proto

syntax = "proto3";

package notification.endpoint.presentation;

import "notification/endpoint/presentation/create_device.proto";

service NotificationEndpointService {
  // Command
  rpc CreateDevice(CreateDeviceRequest) returns (CreateDeviceResponse) {}
}
notification/endpoint/presentation/create_device.proto

syntax = "proto3";

package notification.endpoint.presentation;

message CreateDeviceRequest {
  string name = 1;
}

message CreateDeviceResponse {}
import '{source_root}/notification/endpoint/presentation/service.proto' file in postman

set '{source_root}' in postman's import paths


curl --location --globoff '{{[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user' \
--data ''
{
    "data": [
        {
            "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
            "username": "cgkjl@fjkdsf.co",
            "name": "jsdfgsdgfdgdfdfgs",
            "last_name": "fghfghgfhfggz",
            "created_at": "2022-06-02T12:40:43.632Z",
            "updated_at": "2022-06-02T12:40:43.632Z"
        },
        {
            "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
            "username": "cgkjl@fjkdsf.co",
            "name": "jsdfgsdgfdgdfdfgs",
            "last_name": "fghfghgfhfggz",
            "created_at": "2022-06-02T12:40:43.632Z",
            "updated_at": "2022-06-02T12:40:43.632Z"
        },
        {
            "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
            "username": "cgkjl@fjkdsf.co",
            "name": "jsdfgsdgfdgdfdfgs",
            "last_name": "fghfghgfhfggz",
            "created_at": "2022-06-02T12:40:43.632Z",
            "updated_at": "2022-06-02T12:40:43.632Z"
        }
    ],
    "detail": {
        "http_code": 200,
        "info": "The request has been successfully processed",
        "status": true
    }
}
curl --location --globoff '{{[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user/{{grateful345i@gmail.com}}'
{
    "data": {
        "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
        "username": "cgkjl@fjkdsf.co",
        "name": "jsdfgsdgfdgdfdfgs",
        "last_name": "fghfghgfhfggz",
        "created_at": "2022-06-02T12:40:43.632Z",
        "updated_at": "2022-06-02T12:40:43.632Z"
    },
    "detail": {
        "http_code": 200,
        "info": "The request has been successfully processed",
        "status": true
    }
}
{

    "username": "grateful345i@gmail.com",
    "password": "2334"
}
curl --location --globoff '{{[[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user/login' \
--data-raw '{

    "username": "joseluis@cloudappi.net",
    "password": "2334"
}'
{
    "data": {
        "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICIwMVRMZXhRLTdaSHVRTzd5UkloZklqZ0FzbHBqLUptbFUzS1p6a0pTcjRNIn0.eyJleHAiOjE2NTQyMDk1ODIsImlhdCI6MTY1NDE3MzU4MiwianRpIjoiMTRkZmRjOTEtNGFhNC00NWZjLWI5YTgtNjdmZGRjMjVmZGEzIiwiaXNzIjoiaHR0cHM6Ly9rZXljbG9hay5jbG91ZGFwcGkubmV0L2F1dGgvcmVhbG1zL0FwaS1xdWFsaXR5IiwiYXVkIjpbInJlYWxtLW1hbmFnZW1lbnQiLCJhY2NvdW50Il0sInN1YiI6IjY2MjJjYWYxLWJiMmMtNDkwZS1iZTUxLTdkYThmZjI2ZDdjOSIsInR5cCI6IkJlYXJlciIsImF6cCI6ImFwaS1xdWFsaXR5LWJhY2tlbmQiLCJzZXNzaW9uX3N0YXRlIjoiZDljZWI0OGEtYmY5Yy00MTFjLTg4ZjYtNjJlZTIxMzNmZDk1IiwiYWNyIjoiMSIsInJlYWxtX2FjY2VzcyI6eyJyb2xlcyI6WyJkZWZhdWx0LXJvbGVzLWFwaS1xdWFsaXR5Il19LCJyZXNvdXJjZV9hY2Nlc3MiOnsicmVhbG0tbWFuYWdlbWVudCI6eyJyb2xlcyI6WyJ2aWV3LXJlYWxtIiwidmlldy1pZGVudGl0eS1wcm92aWRlcnMiLCJtYW5hZ2UtaWRlbnRpdHktcHJvdmlkZXJzIiwiaW1wZXJzb25hdGlvbiIsInJlYWxtLWFkbWluIiwiY3JlYXRlLWNsaWVudCIsIm1hbmFnZS11c2VycyIsInF1ZXJ5LXJlYWxtcyIsInZpZXctYXV0aG9yaXphdGlvbiIsInF1ZXJ5LWNsaWVudHMiLCJxdWVyeS11c2VycyIsIm1hbmFnZS1ldmVudHMiLCJtYW5hZ2UtcmVhbG0iLCJ2aWV3LWV2ZW50cyIsInZpZXctdXNlcnMiLCJ2aWV3LWNsaWVudHMiLCJtYW5hZ2UtYXV0aG9yaXphdGlvbiIsIm1hbmFnZS1jbGllbnRzIiwicXVlcnktZ3JvdXBzIl19LCJhcGktcXVhbGl0eS1iYWNrZW5kIjp7InJvbGVzIjpbImFkbWluIl19LCJhY2NvdW50Ijp7InJvbGVzIjpbIm1hbmFnZS1hY2NvdW50IiwibWFuYWdlLWFjY291bnQtbGlua3MiLCJ2aWV3LXByb2ZpbGUiXX19LCJzY29wZSI6ImVtYWlsIHJvbGVzIHByb2ZpbGUiLCJlbWFpbF92ZXJpZmllZCI6ZmFsc2UsIm9yZ2FuaXphdGlvbiI6W10sIm5hbWUiOiJqb3NlbHVpcyBnb21leiIsInByZWZlcnJlZF91c2VybmFtZSI6Impvc2VsdWlzQGNsb3VkYXBwaS5uZXQiLCJnaXZlbl9uYW1lIjoiam9zZWx1aXMiLCJmYW1pbHlfbmFtZSI6ImdvbWV6In0.ubaHr3HTe46mTMwtvWbgvmjKmko2VZIyvFyYFHQpvj3tqAaO88Wu2ePomNuGgvKev_uJL433hmElPPWDPURqppIuLfhHGwptsfRPNNYld87s8ZMWnLw4Me5oOPNm2Rw7GevmhlWzIGvG48zFrNHQz8gZer9bjPInOhEMp-DMwV9jlX3efY0R8Qa-iXrrtcRql23Ept1tODj07RftkDEBD_FWD39lsi3JSTwvKXKHbEc9GzWZ_6mS_A82C_JE1iTI1hA_2tKdlQ1jEYcxRP8jSDtl40fMkOYRt1kay6ZahMnl9DNmGleNIUjXLrxJRNnJva5bi_ZGM6mVjaVZea3eVQ",
        "expires_in": 36000,
        "refresh_expires_in": 1800,
        "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJiNWZlNTAxOC04YzBiLTQ2YzAtYTQyMS0zNTQyMjUyZWM4ZWUifQ.eyJleHAiOjE2NTQxNzUzODIsImlhdCI6MTY1NDE3MzU4MiwianRpIjoiZmYyNmQ0OTEtM2JmOS00ZDgzLTk5NjQtNDA3ZWI0NDNlZTkxIiwiaXNzIjoiaHR0cHM6Ly9rZXljbG9hay5jbG91ZGFwcGkubmV0L2F1dGgvcmVhbG1zL0FwaS1xdWFsaXR5IiwiYXVkIjoiaHR0cHM6Ly9rZXljbG9hay5jbG91ZGFwcGkubmV0L2F1dGgvcmVhbG1zL0FwaS1xdWFsaXR5Iiwic3ViIjoiNjYyMmNhZjEtYmIyYy00OTBlLWJlNTEtN2RhOGZmMjZkN2M5IiwidHlwIjoiUmVmcmVzaCIsImF6cCI6ImFwaS1xdWFsaXR5LWJhY2tlbmQiLCJzZXNzaW9uX3N0YXRlIjoiZDljZWI0OGEtYmY5Yy00MTFjLTg4ZjYtNjJlZTIxMzNmZDk1Iiwic2NvcGUiOiJlbWFpbCByb2xlcyBwcm9maWxlIn0.qUdcdVWz0IAg4Pr0GuKvxc0haNk3q16s7DjeROykwSI",
        "token_type": "Bearer",
        "not-before-policy": 0,
        "session_state": "d9ceb48a-bf9c-411c-88f6-62ee2133fd95",
        "scope": "email roles profile"
    },
    "detail": {
        "http_code": 200,
        "info": "The request has been successfully processed",
        "status": true
    }
}
curl --location --globoff '{{[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user' \
--data-raw '{
   
   "username":"ul@cloudappi.net",
   "emailVerified":true,
   "firstName":"dar",
   "lastName":"dar",
   "password": "2334"
   
}'
$ npm install openapi-to-postmanv2
If you want to use the converter in the CLI, install it globally with NPM:

$ npm i -g openapi-to-postmanv2
📖 Command Line Interface

The converter can be used as a CLI tool as well. The following command line options are available.

openapi2postmanv2 [options]

Options

-s <source>, --spec <source> Used to specify the OpenAPI specification (file path) which is to be converted

-o <destination>, --output <destination> Used to specify the destination file in which the collection is to be written

-p, --pretty Used to pretty print the collection object while writing to a file

-i, --interface-version Specifies the interface version of the converter to be used. Value can be 'v2' or 'v1'. Default is 'v2'.

-O, --options Used to supply options to the converter, for complete options details see here

-c, --options-config Used to supply options to the converter through config file, for complete options details see here

-t, --test Used to test the collection with an in-built sample specification

-v, --version Specifies the version of the converter

-h, --help Specifies all the options along with a few usage examples on the terminal

Usage

Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options
$ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,includeAuthInfoInExample=false
Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options via config file
$ openapi2postmanv2 -s spec.yaml -o collection.json -p  -c ./examples/cli-options-config.json
Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options (Also avoids any "<Error: Too many levels of nesting to fake this schema>" kind of errors present in converted collection)
$ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,requestParametersResolution=Example,optimizeConversion=false,stackLimit=50
$ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,includeAuthInfoInExample=false
Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options via config file
$ openapi2postmanv2 -s spec.yaml -o collection.json -p  -c ./examples/cli-options-config.json
Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options (Also avoids any "<Error: Too many levels of nesting to fake this schema>" kind of errors present in converted collection)
$ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,requestParametersResolution=Example,optimizeConversion=false,stackLimit=50
Testing the converter
$ openapi2postmanv2 --test
🛠 Using the converter as a NodeJS module

In order to use the convert in your node application, you need to import the package using require.

var Converter = require('openapi-to-postmanv2')
The converter provides the following functions:

Convert

The convert function takes in your OpenAPI 3.0, 3.1 and Swagger 2.0 specification ( YAML / JSON ) and converts it to a Postman collection.

Signature: convert (data, options, callback);

data:

{ type: 'file', data: 'filepath' }
OR
{ type: 'string', data: '<entire OpenAPI string - JSON or YAML>' }
OR
{ type: 'json', data: OpenAPI-JS-object }
options:

{
  schemaFaker: true,
  requestNameSource: 'fallback',
  indentCharacter: ' '
}
/*
All three properties are optional. Check the options section below for possible values for each option.
*/
Note: All possible values of options and their usage can be found over here: OPTIONS.md

callback:

function (err, result) {
  /*
  result = {
    result: true,
    output: [
      {
        type: 'collection',
        data: {..collection object..}
      }
    ]
  }
  */
}
Options

Check out complete list of options and their usage at OPTIONS.md

ConversionResult

result - Flag responsible for providing a status whether the conversion was successful or not.

reason - Provides the reason for an unsuccessful conversion, defined only if result if false.

output - Contains an array of Postman objects, each one with a type and data. The only type currently supported is collection.

Sample Usage

const fs = require('fs'),
  Converter = require('openapi-to-postmanv2'),
  openapiData = fs.readFileSync('sample-spec.yaml', {encoding: 'UTF8'});

Converter.convert({ type: 'string', data: openapiData },
  {}, (err, conversionResult) => {
    if (!conversionResult.result) {
      console.log('Could not convert', conversionResult.reason);
    }
    else {
      console.log('The collection object is: ', conversionResult.output[0].data);
    }
  }
);
Validate Function

The validate function is meant to ensure that the data that is being passed to the convert function is a valid JSON object or a valid (YAML/JSON) string.

The validate function is synchronous and returns a status object which conforms to the following schema

Validation object schema

{
  type: 'object',
  properties: {
    result: { type: 'boolean'},
    reason: { type: 'string' }
  },
  required: ['result']
}
  text/plain; charset=utf-8
  application/json
  application/vnd.github+json
  application/vnd.github.v3+json
  application/vnd.github.v3.raw+json
  application/vnd.github.v3.text+json
  application/vnd.github.v3.html+json
  application/vnd.github.v3.full+json
  application/vnd.github.v3.diff
  application/vnd.github.v3.patch{
   "field": [ 1, 2, 3 ]
}{
  "type": "oauth2",
  "flows": {
    "implicit": {
      "authorizationUrl": "https://example.com/api/oauth/dialog",
      "scopes": {
        "write:pets": "modify pets in your account",
        "read:pets": "read your pets"
      }
    },
    "authorizationCode": {
      "authorizationUrl": "https://example.com/api/oauth/dialog",
      "tokenUrl": "https://example.com/api/oauth/token",
      "scopes": {
        "write:pets": "modify pets in your account",
        "read:pets": "read your pets"
      }
    }
  }
}
type: oauth2
flows:
  implicit:
    authorizationUrl: https://example.com/api/oauth/dialog
    scopes:
      write:pets: modify pets in your account
      read:pets: read your pets
  authorizationCode:
    authorizationUrl: https://example.com/api/oauth/dialog
    tokenUrl: https://example.com/api/oauth/token
    scopes:
      write:pets: modify pets in your account
      read:pets: read your pets
{
  "api_key": []
}
api_key: []
OAuth2 Security Requirement

{
  "petstore_auth": [
    "write:pets",
    "read:pets"
  ]
}
petstore_auth:
- write:pets
- read:pets{
  "get": {
    "description": "Returns pets based on ID",
    "summary": "Find pets by ID",
    "operationId": "getPetsById",
    "responses": {
      "200": {
        "description": "pet response",
        "content": {
          "*/*": {
            "schema": {
              "type": "array",
              "items": {
                "$ref": "#/components/schemas/Pet"
              }
            }
          }
        }
      },
      "default": {
        "description": "error payload",
        "content": {
          "text/html": {
            "schema": {
              "$ref": "#/components/schemas/ErrorModel"
            }
          }
        }
      }
    }
  },
  "parameters": [
    {
      "name": "id",
      "in": "path",
      "description": "ID of pet to use",
      "required": true,
      "schema": {
        "type": "array",
        "items": {
          "type": "string"
        }
      },
      "style": "simple"
    }
  ]
}
get:
  description: Returns pets based on ID
  summary: Find pets by ID
  operationId: getPetsById
  responses:
    '200':
      description: pet response
      content:
        '*/*' :
          schema:
            type: array
            items:
              $ref: '#/components/schemas/Pet'
    default:
      description: error payload
      content:
        'text/html':
          schema:
            $ref: '#/components/schemas/ErrorModel'
parameters:
- name: id
  in: path
  description: ID of pet to use
  required: true
  schema:
    type: array
    style: simple
    items:
      type: string 
Operation Object

Describes a single API operation on a path.

Fixed Fields

Field Name	Type	Description
tags	[string]	A list of tags for API documentation control. Tags can be used for logical grouping of operations by resources or any other qualifier.
summary	string	A short summary of what the operation does.
description	string	A verbose explanation of the operation behavior. CommonMark syntax MAY be used for rich text representation.
externalDocs	External Documentation Object	Additional external documentation for this operation.
operationId	string	Unique string used to identify the operation. The id MUST be unique among all operations described in the API. The operationId value is case-sensitive. Tools and libraries MAY use the operationId to uniquely identify an operation, therefore, it is RECOMMENDED to follow common programming naming conventions.
parameters	[Parameter Object | Reference Object]	A list of parameters that are applicable for this operation. If a parameter is already defined at the Path Item, the new definition will override it but can never remove it. The list MUST NOT include duplicated parameters. A unique parameter is defined by a combination of a name and location. The list can use the Reference Object to link to parameters that are defined at the OpenAPI Object's components/parameters.
requestBody	Request Body Object | Reference Object	The request body applicable for this operation. The requestBody is only supported in HTTP methods where the HTTP 1.1 specification RFC7231 has explicitly defined semantics for request bodies. In other cases where the HTTP spec is vague, requestBody SHALL be ignored by consumers.
responses	Responses Object	REQUIRED. The list of possible responses as they are returned from executing this operation.
callbacks	Map[string, Callback Object | Reference Object]	A map of possible out-of band callbacks related to the parent operation. The key is a unique identifier for the Callback Object. Each value in the map is a Callback Object that describes a request that may be initiated by the API provider and the expected responses. The key value used to identify the callback object is an expression, evaluated at runtime, that identifies a URL to use for the callback operation.
deprecated	boolean	Declares this operation to be deprecated. Consumers SHOULD refrain from usage of the declared operation. Default value is false.
security	[Security Requirement Object]	A declaration of which security mechanisms can be used for this operation. The list of values includes alternative security requirement objects that can be used. Only one of the security requirement objects need to be satisfied to authorize a request. This definition overrides any declared top-level security. To remove a top-level security declaration, an empty array can be used.
servers	[Server Object]	An alternative server array to service this operation. If an alternative server object is specified at the Path Item Object or Root level, it will be overridden by this value.
This object MAY be extended with Specification Extensions.

Operation Object Example

{
  "tags": [
    "pet"
  ],
  "summary": "Updates a pet in the store with form data",
  "operationId": "updatePetWithForm",
  "parameters": [
    {
      "name": "petId",
      "in": "path",
      "description": "ID of pet that needs to be updated",
      "required": true,
      "schema": {
        "type": "string"
      }
    }
  ],
  "requestBody": {
    "content": {
      "application/x-www-form-urlencoded": {
        "schema": {
          "type": "object",
           "properties": {
              "name": {
                "description": "Updated name of the pet",
                "type": "string"
              },
              "status": {
                "description": "Updated status of the pet",
                "type": "string"
             }
           },
        "required": ["status"]
        }
      }
    }
  },
  "responses": {
    "200": {
      "description": "Pet updated.",
      "content": {
        "application/json": {},
        "application/xml": {}
      }
    },
    "405": {
      "description": "Method Not Allowed",
      "content": {
        "application/json": {},
        "application/xml": {}
      }
    }
  },
  "security": [
    {
      "petstore_auth": [
        "write:pets",
        "read:pets"
      ]
    }
  ]
}
tags:
- pet
summary: Updates a pet in the store with form data
operationId: updatePetWithForm
parameters:
- name: petId
  in: path
  description: ID of pet that needs to be updated
  required: true
  schema:
    type: string
requestBody:
  content:
    'application/x-www-form-urlencoded':
      schema:
       properties:
          name:
            description: Updated name of the pet
            type: string
          status:
            description: Updated status of the pet
            type: string
       required:
         - status
responses:
  '200':
    description: Pet updated.
    content:
      'application/json': {}
      'application/xml': {}
  '405':
    description: Method Not Allowed
    content:
      'application/json': {}
      'application/xml': {}
security:
- petstore_auth:
  - write:pets
  - read:pets
{
  "name": "Apache 2.0",
  "url": "https://www.apache.org/licenses/LICENSE-2.0.html"
}name: Apache 2.0
url: https://www.apache.org/licenses/LICENSE-2.0.html{
  "url": "https://development.gigantic-server.com/v1",
  "description": "Development server"
}
url: https://development.gigantic-server.com/v1
description: Development server
The following shows how multiple servers can be described, for example, at the OpenAPI Object's servers:

{
  "servers": [
    {
      "url": "https://development.gigantic-server.com/v1",
      "description": "Development server"
    },
    {
      "url": "https://staging.gigantic-server.com/v1",
      "description": "Staging server"
    },
    {
      "url": "https://api.gigantic-server.com/v1",
      "description": "Production server"
    }
  ]
}
servers:
- url: https://development.gigantic-server.com/v1
  description: Development server
- url: https://staging.gigantic-server.com/v1
  description: Staging server
- url: https://api.gigantic-server.com/v1
  description: Production server
The following shows how variables can be used for a server configuration:

{
  "servers": [
    {
      "url": "https://{username}.gigantic-server.com:{port}/{basePath}",
      "description": "The production API server",
      "variables": {
        "username": {
          "default": "demo",
          "description": "this value is assigned by the service provider, in this example `gigantic-server.com`"
        },
        "port": {
          "enum": [
            "8443",
            "443"
          ],
          "default": "8443"
        },
        "basePath": {
          "default": "v2"
        }
      }
    }
  ]
}
servers:
- url: https://{username}.gigantic-server.com:{port}/{basePath}
  description: The production API server
  variables:
    username:
      # note! no enum here means it is an open value
      default: demo
      description: this value is assigned by the service provider, in this example `gigantic-server.com`
    port:
      enum:
        - '8443'
        - '443'
      default: '8443'
    basePath:
      # open meaning there is the opportunity to use special base paths as assigned by the provider, default is `v2`
      default: v2
EADME

License
CommonMark

CommonMark is a rationalized version of Markdown syntax, with a spec and BSD-licensed reference implementations in C and JavaScript.

Try it now!

For more details, see https://commonmark.org.

This repository contains the spec itself, along with tools for running tests against the spec, and for creating HTML and PDF versions of the spec.

The reference implementations live in separate repositories:

https://github.com/commonmark/cmark (C)
https://github.com/commonmark/commonmark.js (JavaScript)
There is a list of third-party libraries in a dozen different languages here.

Running tests against the spec

The spec contains over 500 embedded examples which serve as conformance tests. To run the tests using an executable $PROG:

python3 test/spec_tests.py --program $PROG
If you want to extract the raw test data from the spec without actually running the tests, you can do:

python3 test/spec_tests.py --dump-tests
and you'll get all the tests in JSON format.

JavaScript developers may find it more convenient to use the commonmark-spec npm package, which is published from this repository. It exports an array tests of JSON objects with the format

{
  "markdown": "Foo\nBar\n---\n",
  "html": "<h2>Foo\nBar</h2>\n",
  "section": "Setext headings",
  "number": 65
}
The spec

The source of the spec is spec.txt. This is basically a Markdown file, with code examples written in a shorthand form:

```````````````````````````````` example
Markdown source
.
expected HTML output
````````````````````````````````

> these are two

> blockquotes

> this is a single
>
> blockquote with two paragraphs

pm.variables.has(variableName:String):function → Boolean
Get the value of the Postman variable with the specified name:
pm.variables.get(variableName:String):function → *
Set a local variable with the specified name and value:
pm.variables.set(variableName:String, variableValue:*):function
Return the resolved value of a dynamic variable inside a script using the syntax {{$variableName}}:
pm.variables.replaceIn(variableName:String):function: → *
For example:

const stringWithVars = pm.variables.replaceIn("Hi, my name is {{$randomFirstName}}");
console.log(stringWithVars);
Return an object containing all variables with their values in the current scope. Based on the order of precedence, this will contain variables from multiple scopes.
pm.variables.toObject():function → Object
postman.setNextRequest(requestName:String):Function
Run the specified request after this one (the request ID returned by pm.info.requestId):
postman.setNextRequest(requestId:String):Function
For example:

//script in another request calls:
//pm.environment.set('next', pm.info.requestId)
postman.setNextRequest(pm.environment.get('next'));
Scripting Postman Visualizations

Use pm.visualizer.set to specify a template to display response data in the Postman Visualizer.

pm.visualizer.set(layout:String, data:Object, options:Object):Function
layout required
Handlebars HTML template string
data optional
JSON object that binds to the template and you can access it inside the template string
options optional
Options object for Handlebars.compile()
Example usage:

var template = `<p>{{res.info}}</p>`;
pm.visualizer.set(template, {
    res: pm.response.json()
});
Building response data into Postman Visualizations

Use pm.getData to retrieve response data inside a Postman Visualizer template string.

pm.getData(callback):Function
The callback function accepts two parameters:

error
Any error detail
data
Data passed to the template by pm.visualizer.set
Example usage:

pm.getData(function (error, data) {
  var value = data.res.info;
});
Writing test assertions

pm.test(testName:String, specFunction:Function):Function
You can use pm.test to write test specifications inside either the Pre-request or Tests scripts. Tests include a name and assertion—Postman will output test results as part of the response.

The pm.test method returns the pm object, making the call chainable. The following sample test checks that a response is valid to proceed.

pm.test("response should be okay to process", function () {
  pm.response.to.not.be.error;
  pm.response.to.have.jsonBody('');
  pm.response.to.not.have.jsonBody('error');
});
An optional done callback can be passed to pm.test, to test asynchronous functions.

pm.test('async test', function (done) {
  setTimeout(() => {
    pm.expect(pm.response.code).to.equal(200);
    done();
  }, 1500);
});
Get the total number of tests executed from a specific location in code:
pm.test.index():Function → Number
The pm.expect method allows you to write assertions on your response data, using ChaiJS expect BDD syntax.

pm.expect(assertion:*):Function → Assertion
You can also use pm.response.to.have.* and pm.response.to.be.* to build your assertions.

See Test examples for more assertions.

Using external libraries

require(moduleName:String):function → *
The require method allows you to use the 

> npm install postman-collection --save
Getting Started
In this example snippet we will get started by loading a collection from a file and output the same in console.

var fs = require('fs'), // needed to read JSON file from disk
	Collection = require('postman-collection').Collection,
	myCollection;

// Load a collection to memory from a JSON file on disk (say, sample-collection.json)
myCollection = new Collection(JSON.parse(fs.readFileSync('sample-collection.json').toString()));

// log items at root level of the collection
console.log(myCollection.toJSON());
# Create a folder
$ mkdir actions-runner && cd actions-runner
# Download the latest runner package
$ curl -o actions-runner-linux-arm-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-linux-arm-2.314.1.tar.gz
# Optional: Validate the hash
$ echo "a653dd46dafd47c9a3a6637a18161a1445ac6b9c3f6d6b0305be9e1ee65769af  actions-runner-linux-arm-2.314.1.tar.gz" | shasum -a 256 -c
# Extract the installer
$ tar xzf ./actions-runner-linux-arm-2.314.1.tar.gz
Configure
# Create the runner and start the configuration experience
$ ./config.sh --url https://github.com/grateful345/AGENCY-WEBHOOK --token BHAHZGAPZ7TETPSETRUTYETF7TSAQ
# Last step, run it!
$ ./run.sh
Using your self-hosted runner
# Use this YAML in your workflow file for each job
runs-on: self-hosted
folder permissions and long path restrictions on Windows.

# Create a folder under the drive root
$ mkdir actions-runner; cd actions-runner
# Download the latest runner package
$ Invoke-WebRequest -Uri https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-win-arm64-2.314.1.zip -OutFile actions-runner-win-arm64-2.314.1.zip
# Optional: Validate the hash
$ if((Get-FileHash -Path actions-runner-win-arm64-2.314.1.zip -Algorithm SHA256).Hash.ToUpper() -ne 'acc807696d1dcad6fb45f6038f884185c54c48127445c365e86d03adb164a9e2'.ToUpper()){ throw 'Computed checksum did not match' }
# Extract the installer
$ Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$PWD/actions-runner-win-arm64-2.314.1.zip", "$PWD")
Configure
# Create the runner and start the configuration experience
$ ./config.cmd --url https://github.com/grateful345/AGENCY-WEBHOOK --token BHAHZGAPZ7TETPSETRUTYETF7TSAQ
# Run it!
$ ./run.cmd
Using your self-hosted runner
# Use this YAML in your workflow file for each job
runs-on: self-hosted
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/keys
# Create a folder
$ mkdir actions-runner && cd actions-runner
# Download the latest runner package
$ curl -o actions-runner-osx-arm64-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-osx-arm64-2.314.1.tar.gz
# Optional: Validate the hash
$ echo "e34dab0b4707ad9a9db75f5edf47a804e293af853967a5e0e3b29c8c65f3a004  actions-runner-osx-arm64-2.314.1.tar.gz" | shasum -a 256 -c
# Extract the installer
$ tar xzf ./actions-runner-osx-arm64-2.314.1.tar.gz
Configure
# Create the runner and start the configuration experience
$ ./config.sh --url https://github.com/grateful345/AGENCY-WEBHOOK --token BHAHZGAPZ7TETPSETRUTYETF7TSAQ
# Last step, run it!
$ ./run.sh
Using your self-hosted runner
# Use this YAML in your workflow file for each job
runs-on: self-hosted

{
  "type": "array",
  "items": {
    "title": "Deploy Key",
    "description": "An SSH key granting access to a single repository.",
    "type": "object",
    "properties": {
      "id": {
        "type": "integer"
      },
      "key": {
        "type": "string"
      },
      "url": {
        "type": "string"
      },
      "title": {
        "type": "string"
      },
      "verified": {
        "type": "boolean"
      },
      "created_at": {
        "type": "string"
      },
      "read_only": {
        "type": "boolean"
      },
      "added_by": {
        "type": [
          "string",
          "null"
        ]
      },
      "last_used": {
        "type": [
          "string",
          "null"
        ]
      }
    },
    "required": [
      "id",
      "key",
      "url",
      "title",
      "verified",
      "created_at",
      "read_only"
    ]
  }
}

curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/keys \
  -d '{"title":"octocat@octomac","key":"ssh-rsa AAA...","read_only":true}'

{
  "title": "Deploy Key",
  "description": "An SSH key granting access to a single repository.",
  "type": "object",
  "properties": {
    "id": {
      "type": "integer"
    },
    "key": {
      "type": "string"
    },
    "url": {
      "type": "string"
    },
    "title": {
      "type": "string"
    },
    "verified": {
      "type": "boolean"
    },
    "created_at": {
      "type": "string"
    },
    "read_only": {
      "type": "boolean"
    },
    "added_by": {
      "type": [
        "string",
        "null"
      ]
    },
    "last_used": {
      "type": [
        "string",
        "null"
      ]
    }
  },
  "required": [
    "id",
    "key",
    "url",
    "title",
    "verified",
    "created_at",
    "read_only"
  ]
}

curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/keys/KEY_ID

{
    "image": "mcr.microsoft.com/devcontainers/base:ubuntu"
}
However, [Dockerfiles](https://docs.docker.com/engine/reference/builder/) are a great way to extend images, add additional native OS packages, or make minor edits to the OS image. You can reuse any Dockerfile, but let’s walk through how to create one from scratch.

First, add a file named Dockerfile next to your devcontainer.json. For example:

FROM mcr.microsoft.com/devcontainers/base:ubuntu
# Install the xz-utils package
RUN apt-get update && apt-get install -y xz-utils
Next, remove the image property from devcontainer.json (if it exists) and add the build and dockerfile properties instead:

{
    "build": {
        // Path is relative to the devcontainer.json file.
        "dockerfile": "Dockerfile"
    }
}

YAML
name: Comment when opened
on:
  issues:
    types:
      - opened
jobs:
  comment:
    runs-on: ubuntu-latest
    steps:
      - run: gh issue comment $ISSUE --body "Thank you for opening this issue!"
        env:
          GH_TOKEN: ${{ BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}
          ISSUE: ${{ github.event.issue.html_url }}
You can also execute API calls through GitHub CLI. For example, this workflow first uses the gh api subcommand to query the GraphQL API and parse the result. Then it stores the result in an environment variable that it can access in a later step. In the second step, it uses the gh issue create subcommand to create an issue containing the information from the first step.

YAML
name: Report remaining open issues
on: 
  schedule: 
    # Daily at 8:20 UTC
    - cron: '20 8 * * *'
jobs:
  track_pr:
    runs-on: ubuntu-latest
    steps:
      - run: |
          numOpenIssues="$(gh api graphql -F owner=$OWNER -F name=$REPO -f query='
            query($name: String!, $owner: String!) {
              repository(owner: $Grateful345, name: $keith_Bieszczat) {
                issues(states:OPEN){
                  totalCount
                }
              }
            }
          ' --jq '.data.repository.issues.totalCount')"

          echo 'NUM_OPEN_ISSUES='$numOpenIssues >> $GITHUB_ENV
        env:
          GH_TOKEN: ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}
          OWNER: ${{ github.repository_owner }}
          REPO: ${{ Agency Webhook }}
      - run: |
          gh issue create --title "Issue report" --body "$NUM_OPEN_ISSUES issues remaining" --repo $GITHUB_REPOSITORY
        env:
          GH_TOKEN: ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}

name: Open new issue
on: workflow_dispatch

jobs:
  open-issue:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      issues: write
    steps:
      - run: |
          gh issue --repo ${{ Agency Webhook }} \
            create --title "Issue title" --body "Issue body"
        env:
          GH_TOKEN: ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}
[Example 2: calling the REST API](https://docs.github.com/en/actions/security-guides/automatic-token-authentication#example-2-calling-the-rest-api)

You can use the GITHUB_TOKEN to make authenticated API calls. This example workflow creates an issue using the GitHub REST API:

name: Create issue on commit

on: [ push ]

jobs:
  create_issue:
    runs-on: ubuntu-latest
    permissions:
      issues: write
    steps:
      - name: Create issue using REST API
        run: |
          curl --request POST \
          --url https://api.github.com/repos/${{ github.repository }}/issues \
          --header 'authorization: Bearer ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}' \
          --header 'content-type: application/json' \
          --data '{
            "title": "Automated issue for commit: ${{ github.sha }}",
            "body": "This issue was automatically created by the GitHub Action workflow **${{ github.workflow }}**. \n\n The commit hash was: _${{ github.sha }}_."
            }' \
          --fail

curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  "https://api.github.com/user/packages?package_type=container"
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/user/docker/conflicts
curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID/restore

curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions
  curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/restore
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  "https://api.github.com/orgs/ORG/packages?package_type=container"
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  curl -L \
  -X PATCH \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/applications/Iv1.8a61f9b3a7aba766/token \
  -d '{"access_token":"e72e16c7e42f292c6912e7710c838347ae178b4a"}'https://api.github.com/orgs/ORG/docker/conflicts curl --request GET \
--url "https://api.github.com/octocat" \
--header "Authorization: ghu_16C7e42F292c6912E7710c838347Ae178B4a", \
--header "X-GitHub-Api-Version: 2022-11-28"
Note
curl --request POST \
--url "https://api.github.com/applications/YOUR_CLIENT_ID/token" \
--user "YOUR_CLIENT_ID:YOUR_CLIENT_SECRET" \
--header "Accept: application/vnd.github+json" \
--header "X-GitHub-Api-Version: 2022-11-28" \
--data '{
  "access_token": "e72e16c7e42f292c6912e7710c838347ae178b4a"
}'
kubectl get SampleDB                   # find configured databases

kubectl edit SampleDB/example-database # manually change some settings
sudo snap install multipass
Use Multipass to launch an Ubuntu VM with the charm-dev blueprint:

multipass launch --cpus 4 --memory 8G --disk 30G --name tutorial-vm charm-dev 
Open a shell into the VM:

multipass shell tutorial-vm
Verify that you have Juju and two localhost clouds:

juju clouds
Bootstrap a Juju controller into the MicroK8s cloud:

juju bootstrap microk8s tutorial-controller
Add a workspace, or 'model':

juju add-model tutorial-model
Deploy, configure, and integrate a few things

Deploy Mattermost:

juju deploy mattermost-k8s
See more: Charmhub | mattermost-k8s
Deploy PostgreSQL:

juju deploy postgresql-k8s --channel 14/stable --trust
See more: Charmhub | postgresql-k8s
Enable security in your PostgreSQL deployment:

juju deploy tls-certificates-operator
juju config tls-certificates-operator generate-self-signed-certificates="true" ca-common-name="Test CA"
juju integrate postgresql-k8s tls-certificates-operator
Integrate Mattermost with PostgreSQL:

juju integrate mattermost-k8s postgresql-k8s:db
Watch your deployment come to life:

juju status --watch 1s
(Press Ctrl-C to quit. Drop the --watch 1s flag to get the status statically. Use the --relations flag to view more information about your integrations.)

Test your deployment

When everything is in active or idle status, note the IP address and port of Mattermost and pass them to curl:

curl <IP address>:<port>/api/v4/system/ping
You should see the output below:

{"AndroidLatestVersion":"","AndroidMinVersion":"","IosLatestVersion":"","IosMinVersion":"","status":"OK"}
Congratulations!

You now have a Kubernetes deployment consisting of a Mattermost backed by PosgreSQL with TLS-encrypted traffic!

Clean up

Delete your Multipass VM:

multipass delete --purge tutorial-vm
Uninstall Multipass: Linux | macOS | Windows. On Linux:

snap remove multipass
Next steps

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"$ brew install wget
Homebrew installs packages to their own directory and then symlinks their files into /opt/homebrew (on Apple Silicon).

$ cd /opt/homebrew
$ find Cellar
Cellar/wget/1.16.1
Cellar/wget/1.16.1/bin/wget
Cellar/wget/1.16.1/share/man/man1/wget.1

$ ls -l bin
bin/wget -> ../Cellar/wget/1.16.1/bin/wget
Homebrew won’t install files outside its prefix and you can place a Homebrew installation wherever you like.

Trivially create your own Homebrew packages.

$ brew create https://foo.com/foo-1.0.tgz
Created /opt/homebrew/Library/Taps/homebrew/homebrew-core/Formula/foo.rb
It’s all Git and Ruby underneath, so hack away with the knowledge that you can easily revert your modifications and merge upstream updates.

$ brew edit wget # opens in $EDITOR!
Homebrew formulae are simple Ruby scripts:

class Wget < Formula
  homepage "https://www.gnu.org/software/wget/"
  url "https://ftp.gnu.org/gnu/wget/wget-1.15.tar.gz"
  sha256 "52126be8cf1bddd7536886e74c053ad7d0ed2aa89b4b630f76785bac21695fcd"

  def install
    system "./configure", "--prefix=#{prefix}"
    system "make", "install"
  end
end
Homebrew complements macOS (or your Linux system). Install your RubyGems with gem and their dependencies with brew.

“To install, drag this icon…” no more. Homebrew Cask installs macOS apps, fonts and plugins and other non-open source software.

$ brew install --cask firefox
Making a cask is as simple as creating a formula.

$ brew create --cask https://foo.com/foo-1.0.dmg
Editing /opt/homebrew/Library/Taps/homebrew/homebrew-cask/Casks/foo.rb
GET https://formulae.brew.sh/api/formula.json
GET https://formulae.brew.sh/api/cask.json
Response

[
  ...
  {
    "name": "wget",
    "full_name": "wget",
    "tap": "homebrew/core",
    "oldname": null,
    "oldnames": [],
    "aliases": [],
    "versioned_formulae": [],
    "desc": "Internet file retriever",
    "license": "GPL-3.0-or-later",
    "homepage": "https://www.gnu.org/software/wget/",
    "versions": {
      "stable": "1.24.5",
      "head": "HEAD",
      "bottle": true
    },
    "urls": {
      "stable": {
        "url": "https://ftp.gnu.org/gnu/wget/wget-1.24.5.tar.gz",
        "tag": null,
        "revision": null,
        "using": null,
        "checksum": "fa2dc35bab5184ecbc46a9ef83def2aaaa3f4c9f3c97d4bd19dcb07d4da637de"
      },
      "head": {
        "url": "https://git.savannah.gnu.org/git/wget.git",
        "branch": null,
        "using": null
      }
    },
    "revision": 0,
    "version_scheme": 0,
    "bottle": {
      "stable": {
        "rebuild": 0,
        "root_url": "https://ghcr.io/v2/homebrew/core",
        "files": {
          "arm64_sonoma": {
            "cellar": "/opt/homebrew/Cellar",
            "url": "https://ghcr.io/v2/homebrew/core/wget/blobs/sha256:9befdad158e59763fb0622083974a6252878019702d8c961e1bec3a5f5305339",
            "sha256": "9befdad158e59763fb0622083974a6252878019702d8c961e1bec3a5f5305339"
          },
          "arm64_ventura": {
            "cellar": "/opt/homebrew/Cellar",
            "url": "https://ghcr.io/v2/homebrew/core/wget/blobs/sha256:ac4c0330b70dae06eaa8065bfbea78dda277699d1ae8002478017a1bd9cf1908",
            "sha256": "ac4c0330b70dae06eaa8065bfbea78dda277699d1ae8002478017a1bd9cf1908"
          },
          "arm64_monterey": {
            "cellar": "/opt/homebrew/Cellar",
            "url": "https://ghcr.io/v2/homebrew/core/wget/blobs/sha256:02313702fc03880f221d60ce4d0b652c8b44fe68c15609329d757d031bce6bc4",
            "sha256": "02313702fc03880f221d60ce4d0b652c8b44fe68c15609329d757d031bce6bc4"
          },
          "sonoma": {
            "cellar": "/usr/local/Cellar",
            "url": "https://ghcr.io/v2/homebrew/core/wget/blobs/sha256:034528edb247df85f90997aca6a51ddb988a880af6bb571b8473de1702a887af",
            "sha256": "034528edb247df85f90997aca6a51ddb988a880af6bb571b8473de1702a887af"
          },
          "ventura": {
            "cellar": "/usr/local/Cellar",
            "url": "https://ghcr.io/v2/homebrew/core/wget/blobs/sha256:1b7e2f76c90553543a5e25dadf031c6fcfe280f52bf27d89e04006f9d33fd20b",
            "sha256": "1b7e2f76c90553543a5e25dadf031c6fcfe280f52bf27d89e04006f9d33fd20b"
          },
          "monterey": {
            "cellar": "/usr/local/Cellar",
            "url": "https://ghcr.io/v2/homebrew/core/wget/blobs/sha256:ffc49a5064a003006e69f51434ac5f7ec4f4019c161ad32fab22c32697db61cd",
            "sha256": "ffc49a5064a003006e69f51434ac5f7ec4f4019c161ad32fab22c32697db61cd"
          },
          "x86_64_linux": {
            "cellar": "/home/linuxbrew/.linuxbrew/Cellar",
            "url": "https://ghcr.io/v2/homebrew/core/wget/blobs/sha256:6a4642964fe5c4d1cc8cd3507541736d5b984e34a303a814ef550d4f2f8242f9",
            "sha256": "6a4642964fe5c4d1cc8cd3507541736d5b984e34a303a814ef550d4f2f8242f9"
          }
        }
      }
    },
    "pour_bottle_only_if": null,
    "keg_only": false,
    "keg_only_reason": null,
    "options": [],
    "build_dependencies": [
      "pkg-config"
    ],
    "dependencies": [
      "libidn2",
      "openssl@3"
    ],
    "test_dependencies": [],
    "recommended_dependencies": [],
    "optional_dependencies": [],
    "uses_from_macos": [],
    "uses_from_macos_bounds": [],
    "requirements": [],
    "conflicts_with": [],
    "conflicts_with_reasons": [],
    "link_overwrite": [],
    "caveats": null,
    "installed": [
      {
        "version": "1.21.4",
        "used_options": [],
        "built_as_bottle": true,
        "poured_from_bottle": true,
        "time": 1708305941,
        "runtime_dependencies": [
          {
            "full_name": "libunistring",
            "version": "1.1",
            "revision": 0,
            "pkg_version": "1.1",
            "declared_directly": false
          },
          {
            "full_name": "gettext",
            "version": "0.22.4",
            "revision": 0,
            "pkg_version": "0.22.4",
            "declared_directly": false
          },
          {
            "full_name": "libidn2",
            "version": "2.3.7",
            "revision": 0,
            "pkg_version": "2.3.7",
            "declared_directly": true
          },
          {
            "full_name": "ca-certificates",
            "version": "2023-12-12",
            "revision": 0,
            "pkg_version": "2023-12-12",
            "declared_directly": false
          },
          {
            "full_name": "openssl@3",
            "version": "3.2.1",
            "revision": 0,
            "pkg_version": "3.2.1",
            "declared_directly": true
          }
        ],
        "installed_as_dependency": false,
        "installed_on_request": true
      }
    ],
    "linked_keg": "1.21.4",
    "pinned": false,
    "outdated": true,
    "deprecated": false,
    "deprecation_date": null,
    "deprecation_reason": null,
    "disabled": false,
    "disable_date": null,
    "disable_reason": null,
    "post_install_defined": false,
    "service": null,
    "tap_git_head": "81b42f47998424b628e3dd6f99f21d7dc5313a21",
    "ruby_source_path": "Formula/w/wget.rb",
    "ruby_source_checksum": {
      "sha256": "09106703fde5615993203f1af5717494e00cf51016169e5b0ef3c79628b8b923"
    },
    "head_dependencies": {
      "build_dependencies": [
        "autoconf",
        "automake",
        "xz",
        "pkg-config"
      ],
      "dependencies": [
        "gettext",
        "libidn2",
        "openssl@3"
      ],
      "test_dependencies": [],
      "recommended_dependencies": [],
      "optional_dependencies": [],
      "uses_from_macos": [],
      "uses_from_macos_bounds": []
    },
    "variations": {
      "x86_64_linux": {
        "dependencies": [
          "libidn2",
          "openssl@3",
          "util-linux"
        ],
        "head_dependencies": {
          "build_dependencies": [
            "autoconf",
            "automake",
            "xz",
            "pkg-config"
          ],
          "dependencies": [
            "gettext",
            "libidn2",
            "openssl@3",
            "util-linux"
          ],
          "test_dependencies": [],
          "recommended_dependencies": [],
          "optional_dependencies": [],
          "uses_from_macos": [],
          "uses_from_macos_bounds": []
        }
      }
    }
  },
  ...
]
Get formula metadata for a Homebrew/core formula
Get the brew info --json --formula <formula> output for a single, current Homebrew/homebrew-core formula with extra keys containing analytics data and generation date.

GET https://formulae.brew.sh/api/formula/${FORMULA}.json
VariablesGET https://formulae.brew.sh/api/cask/${CASK}.jsonGET
GET https://formulae.brew.sh/api/analytics/${CATEGORY}/homebrew-core/${DAYS}.json
GET https://formulae.brew.sh/api/analytics/cask-install/homebrew-cask/${DAYS}.json
brew install --cask 1kc-razer
brew install aces_container
snap refresh multipass --stable
# or
snap install multipass --stable
webhook:
  url: [http://my-controller-svc/sync](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)
Enabled             *bool  `json:"enabled,omitempty"`
CacheTimeoutSeconds *int
32 `json:"cacheTimeoutSeconds,omitempty"`
CacheCleanupSeconds *int32 `json:"cacheCleanupSeconds,omitempty"`
def sync_map_controller():
  input_list = get_matching_objects(input_resource, input_selector)
  output_list = list()

  foreach input_object in input_list:
    output_list.append(map_hook(input_object))

  reconcile_objects(output_list)
apiVersion: snapshot.k8s.io/v1
kind: SnapshotSchedule
metadata:
  name: my-app-snapshots
spec:
  snapshotInterval: 6h
  snapshotTTL: 10d
  selector:
    matchLabels:
      app: my-app
apiVersion: metacontroller.k8s.io/v1alpha1
kind: MapController
metadata:
  name: snapshotschedule-controller
spec:
  parentResource:
    apiVersion: snapshot.k8s.io/v1
    resource: snapshotschedules
  inputResources:
  - apiVersion: v1
    resource: persistentvolumeclaims
  outputResources:
  - apiVersion: volumesnapshot.external-storage.k8s.io/v1
    resource: volumesnapshots
  resyncPeriodSeconds: 5
  hooks:
    map:
      webhook:https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862
        url: http://snapshotschedule-controller.metacontroller/map
    tombstone:
      webhook:
        url: http://snapshotschedule-controller.metacontroller/tombstone
apiVersion: metacontroller.k8s.io/v1alpha1
kind: MapController
metadata:
  name: snapshotschedule-controller
spec:
  parentResource:
    apiVersion: snapshot.k8s.io/v1
    resource: snapshotschedules
  inputResources:
  - apiVersion: v1
    resource: persistentvolumeclaims
  outputResources:
  - apiVersion: volumesnapshot.external-storage.k8s.io/v1
    resource: volumesnapshots
  resyncPeriodSeconds: 5
  hooks:
    map:
      webhook:https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862
        url: http://snapshotschedule-controller.metacontroller/map
    tombstone:
      webhook:
        url: http://snapshotschedule-controller.metacontroller/tombstone
// Get all matching objects from all input resources.
inputObjects := []Object{}
for _, inputResource := range inputResources {
  inputObjects = append(inputObjects, getMatchingObjects(inputResource, parentSelector)...)
}
// Call the once hook for each input object.
for _, inputObject := range inputObjects {
  // Compute some opaque string identifying this input object.
  mapKey := makeMapKey(inputObject)

  // Gather observed objects of the output resources that are tagged with this key.
  observedOutputs := []Object{}
  for _, outputResource := range outputResources {
    // Gather all outputs owned by this parent.
    allOutputs := getOwnedObjects(outputResource, parent)
    // Filter to only those tagged for this input.
    observedOutputs = append(observedOutputs, filterByMapKey(allOutputs, mapKey)...)
  }

  // Call user's map hook, passing observed state.
  mapResult := mapHook(parent, inputObject, observedOutputs)
  for _, obj := range mapResult.Outputs {
    // Tag outputs to identify which input they came from.
    setMapKey(obj, mapKey)
  }
  // Manage child objects by reconciling observed and desired outputs.
  manageChildren(observedOutputs, mapResult.Outputs)
}status:
  inputs:
    persistentvolumeclaims:
      total: 20
  ...
For each output resource, we will report the total number of objects owned by this parent across all map keys. In addition, we will automatically aggregate conditions found on output objects, and report how many objects we own with that condition set to True.

For example:


status:
  ...
  outputs:
    volumesnapshots:
      total: 100
      ready: 97
  ...
apiVersion: ctl.enisoc.com/v1
kind: CatSet # this resource is served via CRD
metadata:
  name: my-catset
spec:
  template: # embedded Pod template in CRD
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx
        ports:
        - containerPort: 80
          name: web
You create this with apply:


kubectl apply -f catset.yaml
The promise of apply is that it will "apply the changes you’ve made, without overwriting any automated changes to properties you haven’t specified".

As an example, suppose some other automation decides to edit your Pod template and add a sidecar container:


apiVersion: ctl.enisoc.com/v1
kind: CatSet # this resource is served via CRD
metadata:
  name: my-catset
spec:
  template: # embedded Pod template in CRD
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx
        ports:
        - containerPort: 80
          name: web
      - name: sidecar
        image: log-uploader # fake sidecar example
Now suppose you change something in your local file and reapply it:


kubectl apply -f catset.yaml
apiVersion: metacontroller.k8s.io/v1alpha1
kind: DecoratorController
metadata:
  name: call-removal-api
spec:
  hooks:
    finalize:
      version: v1
      webhook:https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862
        url: http://call-removal-api.metacontroller.svc.cluster.local?type=delete    
  resources:
  - apiVersion: helm.toolkit.fluxcd.io/v2beta1
    resource: helmreleases

curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <e72e16c7e42f292c6912e7710c838347ae178b4a>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  {
  "id": 1,
  "url": "https://api.github.com/authorizations/1",
  "scopes": [
    "public_repo",
    "user"
  ],
  "token": "ghu_16C7e42F292c6912E7710c838347Ae178B4a",
  "token_last_eight": "Ae178B4a",
  "hashed_token": "25f94a2a5c7fbaf499c665bc73d67c1c87e496da8985131633ee0a95819db2e8",
  "app": {
    "url": "http://my-github-app.com",
    "name": "my github app",
    "client_id": "Iv1.8a61f9b3a7aba766"
  },
  "note": "optional note",
  "note_url": "http://optional/note/url",
  "updated_at": "2011-09-06T20:39:23Z",
  "created_at": "2011-09-06T17:26:27Z",
  "fingerprint": "jklmnop12345678",
  "expires_at": "2011-09-08T17:26:27Z",
  "user": {
    "login": "octocat",
    "id": 1,
    "node_id": "MDQ6VXNlcjE=",
    "avatar_url": "https://github.com/images/error/octocat_happy.gif",
    "gravatar_id": "",
    "url": "https://api.github.com/users/octocat",
    "html_url": "https://github.com/octocat",
    "followers_url": "https://api.github.com/users/octocat/followers",
    "following_url": "https://api.github.com/users/octocat/following{/other_user}",
    "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
    "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
    "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
    "organizations_url": "https://api.github.com/users/octocat/orgs",
    "repos_url": "https://api.github.com/users/octocat/repos",
    "events_url": "https://api.github.com/users/octocat/events{/privacy}",
    "received_events_url": "https://api.github.com/users/octocat/received_events",
    "type": "User",
    "site_admin": false
  }
}

https://api.github.com/applications/Iv1.8a61f9b3a7aba766/token \
  -d '{"access_token":"e72e16c7e42f292c6912e7710c838347ae178b4a"}'Status: 200
{
  "id": 1,
  "url": "https://api.github.com/authorizations/1",
  "scopes": [
    "public_repo",
    "user"
  ],
  "token": "ghu_16C7e42F292c6912E7710c838347Ae178B4a",
  "token_last_eight": "Ae178B4a",
  "hashed_token": "25f94a2a5c7fbaf499c665bc73d67c1c87e496da8985131633ee0a95819db2e8",
  "app": {
    "url": "http://my-github-app.com",
    "name": "my github app",
    "client_id": "Iv1.8a61f9b3a7aba766"
  },
  "note": "optional note",
  "note_url": "http://optional/note/url",
  "updated_at": "2011-09-06T20:39:23Z",
  "created_at": "2011-09-06T17:26:27Z",
  "fingerprint": "jklmnop12345678",
  "expires_at": "2011-09-08T17:26:27Z",
  "user": {
    "login": "octocat",
    "id": 1,
    "node_id": "MDQ6VXNlcjE=",
    "avatar_url": "https://github.com/images/error/octocat_happy.gif",
    "gravatar_id": "",
    "url": "https://api.github.com/users/octocat",
    "html_url": "https://github.com/octocat",
    "followers_url": "https://api.github.com/users/octocat/followers",
    "following_url": "https://api.github.com/users/octocat/following{/other_user}",
    "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
    "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
    "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
    "organizations_url": "https://api.github.com/users/octocat/orgs",
    "repos_url": "https://api.github.com/users/octocat/repos",
    "events_url": "https://api.github.com/users/octocat/events{/privacy}",
    "received_events_url": "https://api.github.com/users/octocat/received_events",
    "type": "User",
    "site_admin": false
  }
}
Stripe Python Library

pypi Build Status Coverage Status

The Stripe Python library provides convenient access to the Stripe API from applications written in the Python language. It includes a pre-defined set of classes for API resources that initialize themselves dynamically from API responses which makes it compatible with a wide range of versions of the Stripe API.

Documentation

See the Python API docs.

See video demonstrations covering how to use the library.

Installation

You don't need this source code unless you want to modify the package. If you just want to use the package, just run:

pip install --upgrade stripe
Install from source with:

python setup.py install
Requirements

Python 3.6+ (PyPy supported)
Python 2.7 deprecation

The Python Software Foundation (PSF) community announced the end of support of Python 2 on 01 January 2020. Starting with version 6.0.0 Stripe SDK Python packages will no longer support Python 2.7. To continue to get new features and security updates, please make sure to update your Python runtime to Python 3.6+.

The last version of the Stripe SDK that supports Python 2.7 is 5.5.0.

Usage

The library needs to be configured with your account's secret key which is available in your Stripe Dashboard. Set stripe.api_key to its value:

from stripe import StripeClient

client = StripeClient("sk_test_...")

# list customers
customers = client.customers.list()

# print the first customer's email
print(customers.data[0].email)

# retrieve specific Customer
customer = client.customers.retrieve("cus_123456789")

# print that customer's email
print(customer.email)
Handling exceptions

Unsuccessful requests raise exceptions. The class of the exception will reflect the sort of error that occurred. Please see the Api Reference for a description of the error classes you should handle, and for information on how to inspect these errors.

Per-request Configuration

Configure individual requests with the options argument. For example, you can make requests with a specific Stripe Version or as a connected account:

from stripe import StripeClient

client = StripeClient("sk_test_...")

# list customers
client.customers.list(
    options={
        "api_key": "sk_test_...",
        "stripe_account": "acct_...",
        "stripe_version": "2019-02-19",
    }
)

# retrieve single customer
client.customers.retrieve(
    "cus_123456789",
    options={
        "api_key": "sk_test_...",
        "stripe_account": "acct_...",
        "stripe_version": "2019-02-19",
    }
)
Configuring an HTTP Client

You can configure your StripeClient to use urlfetch, requests, pycurl, or urllib2 with the http_client option:

client = StripeClient("sk_test_...", http_client=stripe.UrlFetchClient())
client = StripeClient("sk_test_...", http_client=stripe.RequestsClient())
client = StripeClient("sk_test_...", http_client=stripe.PycurlClient())
client = StripeClient("sk_test_...", http_client=stripe.Urllib2Client())
Without a configured client, by default the library will attempt to load libraries in the order above (i.e. urlfetch is preferred with urllib2 used as a last resort). We usually recommend that people use requests.

Configuring a Proxy

A proxy can be configured with the proxy client option:

client = StripeClient("sk_test_...", proxy="https://user:pass@example.com:1234")
Configuring Automatic Retries

You can enable automatic retries on requests that fail due to a transient problem by configuring the maximum number of retries:

client = StripeClient("sk_test_...", max_network_retries=2)
Various errors can trigger a retry, like a connection error or a timeout, and also certain API responses like HTTP status 409 Conflict.

Idempotency keys are automatically generated and added to requests, when not given, to guarantee that retries are safe.

Logging

The library can be configured to emit logging that will give you better insight into what it's doing. The info logging level is usually most appropriate for production use, but debug is also available for more verbosity.

There are a few options for enabling it:

Set the environment variable STRIPE_LOG to the value debug or info

$ export STRIPE_LOG=debug
Set stripe.log:

import stripe
stripe.log = 'debug'
Enable it through Python's logging module:

import logging
logging.basicConfig()
logging.getLogger('stripe').setLevel(logging.DEBUG)
Accessing response code and headers

You can access the HTTP response code and headers using the last_response property of the returned resource.

customer = client.customers.retrieve(
    "cus_123456789"
)

print(customer.last_response.code)
print(customer.last_response.headers)
Writing a Plugin

If you're writing a plugin that uses the library, we'd appreciate it if you identified using stripe.set_app_info():

stripe.set_app_info("MyAwesomePlugin", version="1.2.34", url="https://myawesomeplugin.info")
This information is passed along when the library makes calls to the Stripe API.

Telemetry

By default, the library sends telemetry to Stripe regarding request latency and feature usage. These numbers help Stripe improve the overall latency of its API for all users, and improve popular features.

You can disable this behavior if you prefer:

stripe.enable_telemetry = False
Types

In v7.1.0 and newer, the library includes type annotations. See the wiki for a detailed guide.

Please note that some annotations use features that were only fairly recently accepted, such as Unpack[TypedDict] that was accepted in January 2023. We have tested that these types are recognized properly by Pyright. Support for Unpack in MyPy is still experimental, but appears to degrade gracefully. Please report an issue if there is anything we can do to improve the types for your type checker of choice.

Types and the Versioning Policy

We release type changes in minor releases. While stripe-python follows semantic versioning, our semantic versions describe the runtime behavior of the library alone. Our type annotations are not reflected in the semantic version. That is, upgrading to a new minor version of stripe-python might result in your type checker producing a type error that it didn't before. You can use a ~=x.x or x.x.* version specifier in your requirements.txt to constrain pip to a certain minor range of stripe-python.

Types and API Versions

The types describe the Stripe API version that was the latest at the time of release. This is the version that your library sends by default. If you are overriding stripe.api_version / stripe_version on the StripeClient, or using a webhook endpoint tied to an older version, be aware that the data you see at runtime may not match the types.

Beta SDKs

Stripe has features in the beta phase that can be accessed via the beta version of this package. We would love for you to try these and share feedback with us before these features reach the stable phase. To install a beta version use pip install with the exact version you'd like to use:

pip install stripe==v8.6.0b1
Note There can be breaking changes between beta versions. Therefore we recommend pinning the package version to a specific beta version in your requirements file or setup.py. This way you can install the same version each time without breaking changes unless you are intentionally looking for the latest beta version.
We highly recommend keeping an eye on when the beta feature you are interested in goes from beta to stable so that you can move from using a beta version of the SDK to the stable version.

If your beta feature requires a Stripe-Version header to be sent, set the stripe.api_version field using the stripe.add_beta_version function:

stripe.add_beta_version("feature_beta", "v3")
Support

New features and bug fixes are released on the latest major version of the Stripe Python library. If you are on an older major version, we recommend that you upgrade to the latest in order to use the new features and bug fixes including those for security vulnerabilities. Older major versions of the package will continue to be available for use, but will not be receiving any updates.

Development

The test suite depends on stripe-mock, so make sure to fetch and run it from a background terminal (stripe-mock's README also contains instructions for installing via Homebrew and other methods):

go install github.com/stripe/stripe-mock@latest
stripe-mock
Run the following command to set up the development virtualenv:

make
Run all tests on all supported Python versions:

make test
Run all tests for a specific Python version (modify -e according to your Python target):

TOX_ARGS="-e py37" make test
Run all tests in a single file:

TOX_ARGS="-e py37 -- tests/api_resources/abstract/test_updateable_api_resource.py" make test
Run a single test suite:

TOX_ARGS="-e py37 -- tests/api_resources/abstract/test_updateable_api_resource.py::TestUpdateableAPIResource" make test
Run a single test:

TOX_ARGS="-e py37 -- tests/api_resources/abstract/test_updateable_api_resource.py::TestUpdateableAPIResource::test_save" make test
Run the linter with:

make lint
The library uses Black for code formatting. Code must be formatted with Black before PRs are submitted, otherwise CI will fail. Run the formatter with:

make fmt
Stripe python gpg key :

gpg --encrypt --recipient 05D02D3D57ABFF46 FILENAME

Key ID: 05D02D3D57ABFF46
Key type: RSA
Key size: 2048 bits
Fingerprint: C330 33E4 B583 FE61 2EDE 877C 05D0 2D3D 57AB FF46
User ID: Stripe <security@stripe.com>
gpg --encrypt --recipient 05D02D3D57ABFF46 FILENAME

Key ID: 05D02D3D57ABFF46
Key type: RSA
Key size: 2048 bits
Fingerprint: C330 33E4 B583 FE61 2EDE 877C 05D0 2D3D 57AB FF46
User ID: Stripe <security@stripe.com>
postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242
{"apikey":"e59a3446-867f-4520-9121-bef3ce8be522"}

pip install timml
To update TimML type:

pip install timml --upgrade
To uninstall TimML type:

pip uninstall timml
Experimental and for radial flow only
import numpy as np
import matplotlib.pyplot as plt
import timml as tml
rw = 5
ml = tml.Model3D(kaq=10, z=np.arange(20, -1, -2), kzoverkh=50)
w = tml.LargeDiameterWell(ml, Qw=100, layers=[0, 1, 2, 3, 4], rw=rw)
rf = tml.Constant(ml, 100, 0, 20)
ml.solve()
Number of elements, Number of equations: 2 , 11
..
solution complete
xg = np.linspace(rw, 50, 100)
h = ml.headalongline(xg, 0)
for i in range(10):
    plt.plot(xg, h[i])
plt.xlim(0, 50)
plt.xticks(np.arange(0, 51, 5))
plt.grid()

qx = ml.disvec(rw, 0)[0]
print(qx * 2 * np.pi * rw)
print(np.sum(qx * 2 * np.pi * rw))
[-1.50511966e+01 -1.54865781e+01 -1.66133444e+01 -1.94936336e+01
 -3.32803095e+01 -6.18665346e-03 -2.60712180e-02  2.81040181e-02
  7.22067838e-03  1.38265742e-02]
-99.90816871499192
ml.head(rw, 0)
array([19.7515328 , 19.75153236, 19.75153185, 19.75153275, 19.75153281,
       19.76498845, 19.77043627, 19.77362338, 19.77547235, 19.7763392 ])
from scipy.special import k0
k0(5 / ml.aq.lab[1:])
array([2.06829668e-03, 6.74900159e-06, 3.32024764e-08, 2.57897091e-10,
       3.46416156e-12, 8.82738725e-14, 4.63575933e-15, 5.37054606e-16,
       1.44345016e-16])
ml.aq.eigvec
array([[ 1.00000000e-01,  4.41707654e-01,  4.25325404e-01,
        -3.98470231e-01,  3.61803399e-01, -3.16227766e-01,
         2.62865556e-01, -2.03030724e-01, -1.38196601e-01,
        -6.99596196e-02],
       [ 1.00000000e-01,  3.98470231e-01,  2.62865556e-01,
        -6.99596196e-02, -1.38196601e-01,  3.16227766e-01,
        -4.25325404e-01,  4.41707654e-01,  3.61803399e-01,
         2.03030724e-01],
       [ 1.00000000e-01,  3.16227766e-01, -3.10776816e-17,
         3.16227766e-01, -4.47213595e-01,  3.16227766e-01,
        -2.38891966e-16, -3.16227766e-01, -4.47213595e-01,
        -3.16227766e-01],
       [ 1.00000000e-01,  2.03030724e-01, -2.62865556e-01,
         4.41707654e-01, -1.38196601e-01, -3.16227766e-01,
         4.25325404e-01, -6.99596196e-02,  3.61803399e-01,
         3.98470231e-01],
       [ 1.00000000e-01,  6.99596196e-02, -4.25325404e-01,
         2.03030724e-01,  3.61803399e-01, -3.16227766e-01,
        -2.62865556e-01,  3.98470231e-01, -1.38196601e-01,
        -4.41707654e-01],
       [ 1.00000000e-01, -6.99596196e-02, -4.25325404e-01,
        -2.03030724e-01,  3.61803399e-01,  3.16227766e-01,
        -2.62865556e-01, -3.98470231e-01, -1.38196601e-01,
         4.41707654e-01],
       [ 1.00000000e-01, -2.03030724e-01, -2.62865556e-01,
        -4.41707654e-01, -1.38196601e-01,  3.16227766e-01,
         4.25325404e-01,  6.99596196e-02,  3.61803399e-01,
        -3.98470231e-01],
       [ 1.00000000e-01, -3.16227766e-01, -2.90992345e-16,
        -3.16227766e-01, -4.47213595e-01, -3.16227766e-01,
        -5.07992125e-17,  3.16227766e-01, -4.47213595e-01,
         3.16227766e-01],
       [ 1.00000000e-01, -3.98470231e-01,  2.62865556e-01,
         6.99596196e-02, -1.38196601e-01, -3.16227766e-01,
        -4.25325404e-01, -4.41707654e-01,  3.61803399e-01,
        -2.03030724e-01],
       [ 1.00000000e-01, -4.41707654e-01,  4.25325404e-01,
         3.98470231e-01,  3.61803399e-01,  3.16227766e-01,
         2.62865556e-01,  2.03030724e-01, -1.38196601e-01,
         6.99596196e-02]]

  curl -v https://mysite.atlassian.net --user me@example.com:ATATT3xFfGF0em-7Sy8fZXMVgrISVS9LAQikknXg7B0GyB-S-vVVTBM37VJoVWyYpdetDBLd1X0SdJk2FH0EorccPwryJm3xsPYum01tZK_yc0_rbXvKV_U__JgGuERBBhZDH-gOpsv4GvsIaTOb74PfUj9JtqBXWlxO_GeQ84aq04QHt54XByw=155E8069 / ATATT3xFfGF0R4NmdY2uSKkW7UbRpFzPiOW4n19gsX7JGvw2OUu-ZkR9rE0tZbJzFaBT-4KQyzF0bLGlves4bxqzl6EhiReof-qs_USU2IFA53f1COSw5ul-L6TIaWfGQ5HJnibbRj-X-8fx9ohj7qd7iXZHDuUQ9Qd5IMOOlUCzwvhhV2gos3g=7D2F2392
/ NcKhKEbWghsh1bSAUXEO1552

![https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator]

![https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862]
![https://characterai.io/static/tti/c/b/c/4/2/4/cbc424ac-52f3-4984-9b35-7e1953f200e9/0.webp]

authentic token NGROK (God's Time Travel Corporation)
--header
'2avvD0NhbrJRkbxHpTCTKBldaL5_4ywouQsYBpunfxgtzZGxT'

authorization key SCP Foundation
--header
'0xh723hfva83445na7fn342h'

curl --location 'https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242

curl --location 'https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}

curl --location 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/2020-07-23' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}

curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location 'https://informatics.netify.ai/api/v1/intelligence/cryptocurrency_node/flows' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'
curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

https://informatics.netify.ai/api/v2/lookup/applications?filter_starts_with=f&filter_application_categories=["4","24"]

curl --location -g 'https://informatics.netify.ai/api/v2/lookup/applications?page=1&settings_limit=5&filter_starts_with=f&filter_application_categories=[%224%22%2C%2224%22]&settings_show_default_logo=false' \
--header 'https://dashboard.stripe.com/': EG' / and 
--header 'https://scp-wiki.wikidot.com/':
EG'
Sample flow metadata from core processor
...
"detected_protocol_name": "HTTPS",
"detected_application_name": "netify.whatsapp.business",
"ssl": {
  "alpn": [
    "h2",
    "http/1.1"
  ],
  "alpn_server": [],
  "version": "0x0303",
  "cipher_suite": "0xc02b",
  "client_sni": "static.whatsapp.net",
  "server_cn": "*.whatsapp.net",
  "client_ja3": "d8c87b9bfde38897979e4124262...",
  "server_ja3": "6e15a5bf660856fa03186247ca4...",
  "issuer_dn": "C=US, O=DigiCert Inc, OU=www...",
  "subject_dn": "C=US, ST=California, L=Menlo..."
},

# /etc/netifyd/plugins.d/10-netify-proc-core.conf

[proc-core]
enable = yes
...
# /etc/netifyd/netify-proc-core.json
{
   "format": "json",
   "compressor": "none",
   "sinks": {
      "sink-socket": {
         "default": {
             "enable": true,
             "types": [ "stream-flows", "stream-stats" ]
          },
          "tcp": {
             "enable": true,
             "types": [ "stream-flows", "stream-stats" ]
          },
      },
      "sink-mqtt": {
         "flows": {
            "enable": false,
            "types": [ "stream-flows" ]
         },
         "stats": {
            "enable": false,
            "types": [ "stream-stats" ]
         }
      }
   }

https://manager.netify.ai/api/v1/assets/agents

curl --location 'https://manager.netify.ai/api/v1/assets/agents' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

curl --location 'https://manager.netify.ai/api/v1/assets/agents/CH-AM-BE-RS' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

curl --location 'https://informatics.netify.ai/api/v2/lookup/platforms/cloudflare'

curl --location 'https://informatics.netify.ai/api/v2/lookup/platforms'

curl --location 'https://informatics.netify.ai/api/v2/lookup/platforms'

curl --location 'https://informatics.netify.ai/api/v2/lookup/domains/twitter.com'

curl --location 'https://informatics.netify.ai/api/v2/lookup/signatures/categories' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'
...
 X-SHA256-Hash: 8cb030f2...
 X-SHA256-Applications-Hash: b01e4196e...

...
 "data_info": {
    "hash": "8cb030f2c4...",
    "applications_hash": "b01e4196e..."
 },

...
 X-SHA256-Hash: b01e4196e...

...
 "data_info": {
    "hash": "b01e4196e...",
    "entries": 16798
 }
curl --location 'https://informatics.netify.ai/api/v2/lookup/signatures/applications?settings_version=4.2.5&settings_format=normal' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v2/lookup/signatures/applications?settings_version=4.2.5&settings_format=normal

https://informatics.netify.ai/api/v1/intelligence/discovery/devices

curl --location 'https://informatics.netify.ai/api/v1/intelligence/discovery/devices' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

curl --location 'https://informatics.netify.ai/api/v1/intelligence/discovery/devices/ac:ed:5c:00:00:00' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard

curl --location 'https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v1/intelligence/tls_versions/statusboard

curl --location 'https://informatics.netify.ai/api/v1/intelligence/discovery/devices/ac:ed:5c:00:00:00' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows

{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}

curl --location 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/flows' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline

curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/anomaly_detection/timeline' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

https://informatics.netify.ai/api/v1/intelligence/ip_reputation/:date

curl --location --request GET 'https://informatics.netify.ai/api/v1/intelligence/ip_reputation/2020-07-23' \
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242' \
--data '{
	"mac": "ac:ed:5c:b7:cc:b7",
	"listname": "firehol_level1",
	"flow_list": [1,2]
}'

curl --location 'https://informatics.netify.ai/api/v2/lookup/applications/twitter'

https://informatics.netify.ai/api/v2/lookup/protocols?filter_starts_with=f&filter_protocol_categories=["2","17"]

curl --location 'https://informatics.netify.ai/api/v2/lookup/protocols?page=1&settings_limit=5'

https://informatics.netify.ai/api/v2/lookup/protocols/:id

curl --location 'https://informatics.netify.ai/api/v2/lookup/protocols/bittorrent'

https://informatics.netify.ai/api/v2/lookup/protocol_categories

curl --location 'https://informatics.netify.ai/api/v2/lookup/protocol_categories' \
--header 'https://scp-wiki.wikidot.com/'
/ and
--header 'https://dashboard.stripe.com/'
/ and
--header '[https://scp-db.fandom.com/wiki/The_Administrator](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)'

...
 X-SHA256-Hash: b01e4196e...

curl --location 'https://informatics.netify.ai/api/v2/lookup/signatures/applications?settings_version=4.2.5&settings_format=normal' \
--header 'postman api key : PMAK-65fcefd7f279ab0001bc1c91-bea679740eef30d16701cb886564e8d242'

SCPiNET 3.7.61
--------
Initiating backup servers...
Accessing SCP-XXXX...
WARNING: Hash sum check failed. Checking file integrity...
Attempting to recover files...
XXXX.scp failed!
XXXX.scp.old success!
XXXX.log success!
XXXX.a.incident failed!
XXXX.b.incident failed!
XXXX.c.incident success!
XXXX.d.incident failed!

<meta name="viewport" content="width=device-width, initial-scale=1.0"/> (all pages)
remove
<meta name="description" content="The SCP Foundation's 'top-secret' archives, declassified for your enjoyment."/> (a


We could not find some of the files imported by the .proto file. Specify import paths to those unresolved files using the options below.
Details: unresolved import: notification/notification/common/notification_code.proto
import file : {source_root}/notification/endpoint/presentation/service.proto
import paths : {source_root}/
However, it works normally in lower versions.

Steps To Reproduce

Write file
notification/endpoint/presentation/service.proto

syntax = "proto3";

package notification.endpoint.presentation;

import "notification/endpoint/presentation/create_device.proto";

service NotificationEndpointService {
  // Command
  rpc CreateDevice(CreateDeviceRequest) returns (CreateDeviceResponse) {}
}
notification/endpoint/presentation/create_device.proto

syntax = "proto3";

package notification.endpoint.presentation;

message CreateDeviceRequest {
  string name = 1;
}

message CreateDeviceResponse {}
import '{source_root}/notification/endpoint/presentation/service.proto' file in postman

set '{source_root}' in postman's import paths


curl --location --globoff '{{[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user' \
--data ''
{
    "data": [
        {
            "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
            "username": "cgkjl@fjkdsf.co",
            "name": "jsdfgsdgfdgdfdfgs",
            "last_name": "fghfghgfhfggz",
            "created_at": "2022-06-02T12:40:43.632Z",
            "updated_at": "2022-06-02T12:40:43.632Z"
        },
        {
            "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
            "username": "cgkjl@fjkdsf.co",
            "name": "jsdfgsdgfdgdfdfgs",
            "last_name": "fghfghgfhfggz",
            "created_at": "2022-06-02T12:40:43.632Z",
            "updated_at": "2022-06-02T12:40:43.632Z"
        },
        {
            "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
            "username": "cgkjl@fjkdsf.co",
            "name": "jsdfgsdgfdgdfdfgs",
            "last_name": "fghfghgfhfggz",
            "created_at": "2022-06-02T12:40:43.632Z",
            "updated_at": "2022-06-02T12:40:43.632Z"
        }
    ],
    "detail": {
        "http_code": 200,
        "info": "The request has been successfully processed",
        "status": true
    }
}
curl --location --globoff '{{[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user/{{grateful345i@gmail.com}}'
{
    "data": {
        "keycloak_id": "6b20cb38-0242-4d41-87aa-339201a2fc6c",
        "username": "cgkjl@fjkdsf.co",
        "name": "jsdfgsdgfdgdfdfgs",
        "last_name": "fghfghgfhfggz",
        "created_at": "2022-06-02T12:40:43.632Z",
        "updated_at": "2022-06-02T12:40:43.632Z"
    },
    "detail": {
        "http_code": 200,
        "info": "The request has been successfully processed",
        "status": true
    }
}
{

    "username": "grateful345i@gmail.com",
    "password": "2334"
}
curl --location --globoff '{{[[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user/login' \
--data-raw '{

    "username": "joseluis@cloudappi.net",
    "password": "2334"
}'
{
    "data": {
        "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICIwMVRMZXhRLTdaSHVRTzd5UkloZklqZ0FzbHBqLUptbFUzS1p6a0pTcjRNIn0.eyJleHAiOjE2NTQyMDk1ODIsImlhdCI6MTY1NDE3MzU4MiwianRpIjoiMTRkZmRjOTEtNGFhNC00NWZjLWI5YTgtNjdmZGRjMjVmZGEzIiwiaXNzIjoiaHR0cHM6Ly9rZXljbG9hay5jbG91ZGFwcGkubmV0L2F1dGgvcmVhbG1zL0FwaS1xdWFsaXR5IiwiYXVkIjpbInJlYWxtLW1hbmFnZW1lbnQiLCJhY2NvdW50Il0sInN1YiI6IjY2MjJjYWYxLWJiMmMtNDkwZS1iZTUxLTdkYThmZjI2ZDdjOSIsInR5cCI6IkJlYXJlciIsImF6cCI6ImFwaS1xdWFsaXR5LWJhY2tlbmQiLCJzZXNzaW9uX3N0YXRlIjoiZDljZWI0OGEtYmY5Yy00MTFjLTg4ZjYtNjJlZTIxMzNmZDk1IiwiYWNyIjoiMSIsInJlYWxtX2FjY2VzcyI6eyJyb2xlcyI6WyJkZWZhdWx0LXJvbGVzLWFwaS1xdWFsaXR5Il19LCJyZXNvdXJjZV9hY2Nlc3MiOnsicmVhbG0tbWFuYWdlbWVudCI6eyJyb2xlcyI6WyJ2aWV3LXJlYWxtIiwidmlldy1pZGVudGl0eS1wcm92aWRlcnMiLCJtYW5hZ2UtaWRlbnRpdHktcHJvdmlkZXJzIiwiaW1wZXJzb25hdGlvbiIsInJlYWxtLWFkbWluIiwiY3JlYXRlLWNsaWVudCIsIm1hbmFnZS11c2VycyIsInF1ZXJ5LXJlYWxtcyIsInZpZXctYXV0aG9yaXphdGlvbiIsInF1ZXJ5LWNsaWVudHMiLCJxdWVyeS11c2VycyIsIm1hbmFnZS1ldmVudHMiLCJtYW5hZ2UtcmVhbG0iLCJ2aWV3LWV2ZW50cyIsInZpZXctdXNlcnMiLCJ2aWV3LWNsaWVudHMiLCJtYW5hZ2UtYXV0aG9yaXphdGlvbiIsIm1hbmFnZS1jbGllbnRzIiwicXVlcnktZ3JvdXBzIl19LCJhcGktcXVhbGl0eS1iYWNrZW5kIjp7InJvbGVzIjpbImFkbWluIl19LCJhY2NvdW50Ijp7InJvbGVzIjpbIm1hbmFnZS1hY2NvdW50IiwibWFuYWdlLWFjY291bnQtbGlua3MiLCJ2aWV3LXByb2ZpbGUiXX19LCJzY29wZSI6ImVtYWlsIHJvbGVzIHByb2ZpbGUiLCJlbWFpbF92ZXJpZmllZCI6ZmFsc2UsIm9yZ2FuaXphdGlvbiI6W10sIm5hbWUiOiJqb3NlbHVpcyBnb21leiIsInByZWZlcnJlZF91c2VybmFtZSI6Impvc2VsdWlzQGNsb3VkYXBwaS5uZXQiLCJnaXZlbl9uYW1lIjoiam9zZWx1aXMiLCJmYW1pbHlfbmFtZSI6ImdvbWV6In0.ubaHr3HTe46mTMwtvWbgvmjKmko2VZIyvFyYFHQpvj3tqAaO88Wu2ePomNuGgvKev_uJL433hmElPPWDPURqppIuLfhHGwptsfRPNNYld87s8ZMWnLw4Me5oOPNm2Rw7GevmhlWzIGvG48zFrNHQz8gZer9bjPInOhEMp-DMwV9jlX3efY0R8Qa-iXrrtcRql23Ept1tODj07RftkDEBD_FWD39lsi3JSTwvKXKHbEc9GzWZ_6mS_A82C_JE1iTI1hA_2tKdlQ1jEYcxRP8jSDtl40fMkOYRt1kay6ZahMnl9DNmGleNIUjXLrxJRNnJva5bi_ZGM6mVjaVZea3eVQ",
        "expires_in": 36000,
        "refresh_expires_in": 1800,
        "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJiNWZlNTAxOC04YzBiLTQ2YzAtYTQyMS0zNTQyMjUyZWM4ZWUifQ.eyJleHAiOjE2NTQxNzUzODIsImlhdCI6MTY1NDE3MzU4MiwianRpIjoiZmYyNmQ0OTEtM2JmOS00ZDgzLTk5NjQtNDA3ZWI0NDNlZTkxIiwiaXNzIjoiaHR0cHM6Ly9rZXljbG9hay5jbG91ZGFwcGkubmV0L2F1dGgvcmVhbG1zL0FwaS1xdWFsaXR5IiwiYXVkIjoiaHR0cHM6Ly9rZXljbG9hay5jbG91ZGFwcGkubmV0L2F1dGgvcmVhbG1zL0FwaS1xdWFsaXR5Iiwic3ViIjoiNjYyMmNhZjEtYmIyYy00OTBlLWJlNTEtN2RhOGZmMjZkN2M5IiwidHlwIjoiUmVmcmVzaCIsImF6cCI6ImFwaS1xdWFsaXR5LWJhY2tlbmQiLCJzZXNzaW9uX3N0YXRlIjoiZDljZWI0OGEtYmY5Yy00MTFjLTg4ZjYtNjJlZTIxMzNmZDk1Iiwic2NvcGUiOiJlbWFpbCByb2xlcyBwcm9maWxlIn0.qUdcdVWz0IAg4Pr0GuKvxc0haNk3q16s7DjeROykwSI",
        "token_type": "Bearer",
        "not-before-policy": 0,
        "session_state": "d9ceb48a-bf9c-411c-88f6-62ee2133fd95",
        "scope": "email roles profile"
    },
    "detail": {
        "http_code": 200,
        "info": "The request has been successfully processed",
        "status": true
    }
}
curl --location --globoff '{{[base_url](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)}}/user' \
--data-raw '{
   
   "username":"ul@cloudappi.net",
   "emailVerified":true,
   "firstName":"dar",
   "lastName":"dar",
   "password": "2334"
   
}'
$ npm install openapi-to-postmanv2
If you want to use the converter in the CLI, install it globally with NPM:

$ npm i -g openapi-to-postmanv2
📖 Command Line Interface

The converter can be used as a CLI tool as well. The following command line options are available.

openapi2postmanv2 [options]

Options

-s <source>, --spec <source> Used to specify the OpenAPI specification (file path) which is to be converted

-o <destination>, --output <destination> Used to specify the destination file in which the collection is to be written

-p, --pretty Used to pretty print the collection object while writing to a file

-i, --interface-version Specifies the interface version of the converter to be used. Value can be 'v2' or 'v1'. Default is 'v2'.

-O, --options Used to supply options to the converter, for complete options details see here

-c, --options-config Used to supply options to the converter through config file, for complete options details see here

-t, --test Used to test the collection with an in-built sample specification

-v, --version Specifies the version of the converter

-h, --help Specifies all the options along with a few usage examples on the terminal

Usage

Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options
$ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,includeAuthInfoInExample=false
Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options via config file
$ openapi2postmanv2 -s spec.yaml -o collection.json -p  -c ./examples/cli-options-config.json
Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options (Also avoids any "<Error: Too many levels of nesting to fake this schema>" kind of errors present in converted collection)
$ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,requestParametersResolution=Example,optimizeConversion=false,stackLimit=50
$ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,includeAuthInfoInExample=false
Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options via config file
$ openapi2postmanv2 -s spec.yaml -o collection.json -p  -c ./examples/cli-options-config.json
Takes a specification (spec.yaml) as an input and writes to a file (collection.json) with pretty printing and using provided options (Also avoids any "<Error: Too many levels of nesting to fake this schema>" kind of errors present in converted collection)
$ openapi2postmanv2 -s spec.yaml -o collection.json -p -O folderStrategy=Tags,requestParametersResolution=Example,optimizeConversion=false,stackLimit=50
Testing the converter
$ openapi2postmanv2 --test
🛠 Using the converter as a NodeJS module

In order to use the convert in your node application, you need to import the package using require.

var Converter = require('openapi-to-postmanv2')
The converter provides the following functions:

Convert

The convert function takes in your OpenAPI 3.0, 3.1 and Swagger 2.0 specification ( YAML / JSON ) and converts it to a Postman collection.

Signature: convert (data, options, callback);

data:

{ type: 'file', data: 'filepath' }
OR
{ type: 'string', data: '<entire OpenAPI string - JSON or YAML>' }
OR
{ type: 'json', data: OpenAPI-JS-object }
options:

{
  schemaFaker: true,
  requestNameSource: 'fallback',
  indentCharacter: ' '
}
/*
All three properties are optional. Check the options section below for possible values for each option.
*/
Note: All possible values of options and their usage can be found over here: OPTIONS.md

callback:

function (err, result) {
  /*
  result = {
    result: true,
    output: [
      {
        type: 'collection',
        data: {..collection object..}
      }
    ]
  }
  */
}
Options

Check out complete list of options and their usage at OPTIONS.md

ConversionResult

result - Flag responsible for providing a status whether the conversion was successful or not.

reason - Provides the reason for an unsuccessful conversion, defined only if result if false.

output - Contains an array of Postman objects, each one with a type and data. The only type currently supported is collection.

Sample Usage

const fs = require('fs'),
  Converter = require('openapi-to-postmanv2'),
  openapiData = fs.readFileSync('sample-spec.yaml', {encoding: 'UTF8'});

Converter.convert({ type: 'string', data: openapiData },
  {}, (err, conversionResult) => {
    if (!conversionResult.result) {
      console.log('Could not convert', conversionResult.reason);
    }
    else {
      console.log('The collection object is: ', conversionResult.output[0].data);
    }
  }
);
Validate Function

The validate function is meant to ensure that the data that is being passed to the convert function is a valid JSON object or a valid (YAML/JSON) string.

The validate function is synchronous and returns a status object which conforms to the following schema

Validation object schema

{
  type: 'object',
  properties: {
    result: { type: 'boolean'},
    reason: { type: 'string' }
  },
  required: ['result']
}
  text/plain; charset=utf-8
  application/json
  application/vnd.github+json
  application/vnd.github.v3+json
  application/vnd.github.v3.raw+json
  application/vnd.github.v3.text+json
  application/vnd.github.v3.html+json
  application/vnd.github.v3.full+json
  application/vnd.github.v3.diff
  application/vnd.github.v3.patch{
   "field": [ 1, 2, 3 ]
}{
  "type": "oauth2",
  "flows": {
    "implicit": {
      "authorizationUrl": "https://example.com/api/oauth/dialog",
      "scopes": {
        "write:pets": "modify pets in your account",
        "read:pets": "read your pets"
      }
    },
    "authorizationCode": {
      "authorizationUrl": "https://example.com/api/oauth/dialog",
      "tokenUrl": "https://example.com/api/oauth/token",
      "scopes": {
        "write:pets": "modify pets in your account",
        "read:pets": "read your pets"
      }
    }
  }
}
type: oauth2
flows:
  implicit:
    authorizationUrl: https://example.com/api/oauth/dialog
    scopes:
      write:pets: modify pets in your account
      read:pets: read your pets
  authorizationCode:
    authorizationUrl: https://example.com/api/oauth/dialog
    tokenUrl: https://example.com/api/oauth/token
    scopes:
      write:pets: modify pets in your account
      read:pets: read your pets
{
  "api_key": []
}
api_key: []
OAuth2 Security Requirement

{
  "petstore_auth": [
    "write:pets",
    "read:pets"
  ]
}
petstore_auth:
- write:pets
- read:pets{
  "get": {
    "description": "Returns pets based on ID",
    "summary": "Find pets by ID",
    "operationId": "getPetsById",
    "responses": {
      "200": {
        "description": "pet response",
        "content": {
          "*/*": {
            "schema": {
              "type": "array",
              "items": {
                "$ref": "#/components/schemas/Pet"
              }
            }
          }
        }
      },
      "default": {
        "description": "error payload",
        "content": {
          "text/html": {
            "schema": {
              "$ref": "#/components/schemas/ErrorModel"
            }
          }
        }
      }
    }
  },
  "parameters": [
    {
      "name": "id",
      "in": "path",
      "description": "ID of pet to use",
      "required": true,
      "schema": {
        "type": "array",
        "items": {
          "type": "string"
        }
      },
      "style": "simple"
    }
  ]
}
get:
  description: Returns pets based on ID
  summary: Find pets by ID
  operationId: getPetsById
  responses:
    '200':
      description: pet response
      content:
        '*/*' :
          schema:
            type: array
            items:
              $ref: '#/components/schemas/Pet'
    default:
      description: error payload
      content:
        'text/html':
          schema:
            $ref: '#/components/schemas/ErrorModel'
parameters:
- name: id
  in: path
  description: ID of pet to use
  required: true
  schema:
    type: array
    style: simple
    items:
      type: string 
Operation Object

Describes a single API operation on a path.

Fixed Fields

Field Name	Type	Description
tags	[string]	A list of tags for API documentation control. Tags can be used for logical grouping of operations by resources or any other qualifier.
summary	string	A short summary of what the operation does.
description	string	A verbose explanation of the operation behavior. CommonMark syntax MAY be used for rich text representation.
externalDocs	External Documentation Object	Additional external documentation for this operation.
operationId	string	Unique string used to identify the operation. The id MUST be unique among all operations described in the API. The operationId value is case-sensitive. Tools and libraries MAY use the operationId to uniquely identify an operation, therefore, it is RECOMMENDED to follow common programming naming conventions.
parameters	[Parameter Object | Reference Object]	A list of parameters that are applicable for this operation. If a parameter is already defined at the Path Item, the new definition will override it but can never remove it. The list MUST NOT include duplicated parameters. A unique parameter is defined by a combination of a name and location. The list can use the Reference Object to link to parameters that are defined at the OpenAPI Object's components/parameters.
requestBody	Request Body Object | Reference Object	The request body applicable for this operation. The requestBody is only supported in HTTP methods where the HTTP 1.1 specification RFC7231 has explicitly defined semantics for request bodies. In other cases where the HTTP spec is vague, requestBody SHALL be ignored by consumers.
responses	Responses Object	REQUIRED. The list of possible responses as they are returned from executing this operation.
callbacks	Map[string, Callback Object | Reference Object]	A map of possible out-of band callbacks related to the parent operation. The key is a unique identifier for the Callback Object. Each value in the map is a Callback Object that describes a request that may be initiated by the API provider and the expected responses. The key value used to identify the callback object is an expression, evaluated at runtime, that identifies a URL to use for the callback operation.
deprecated	boolean	Declares this operation to be deprecated. Consumers SHOULD refrain from usage of the declared operation. Default value is false.
security	[Security Requirement Object]	A declaration of which security mechanisms can be used for this operation. The list of values includes alternative security requirement objects that can be used. Only one of the security requirement objects need to be satisfied to authorize a request. This definition overrides any declared top-level security. To remove a top-level security declaration, an empty array can be used.
servers	[Server Object]	An alternative server array to service this operation. If an alternative server object is specified at the Path Item Object or Root level, it will be overridden by this value.
This object MAY be extended with Specification Extensions.

Operation Object Example

{
  "tags": [
    "pet"
  ],
  "summary": "Updates a pet in the store with form data",
  "operationId": "updatePetWithForm",
  "parameters": [
    {
      "name": "petId",
      "in": "path",
      "description": "ID of pet that needs to be updated",
      "required": true,
      "schema": {
        "type": "string"
      }
    }
  ],
  "requestBody": {
    "content": {
      "application/x-www-form-urlencoded": {
        "schema": {
          "type": "object",
           "properties": {
              "name": {
                "description": "Updated name of the pet",
                "type": "string"
              },
              "status": {
                "description": "Updated status of the pet",
                "type": "string"
             }
           },
        "required": ["status"]
        }
      }
    }
  },
  "responses": {
    "200": {
      "description": "Pet updated.",
      "content": {
        "application/json": {},
        "application/xml": {}
      }
    },
    "405": {
      "description": "Method Not Allowed",
      "content": {
        "application/json": {},
        "application/xml": {}
      }
    }
  },
  "security": [
    {
      "petstore_auth": [
        "write:pets",
        "read:pets"
      ]
    }
  ]
}
tags:
- pet
summary: Updates a pet in the store with form data
operationId: updatePetWithForm
parameters:
- name: petId
  in: path
  description: ID of pet that needs to be updated
  required: true
  schema:
    type: string
requestBody:
  content:
    'application/x-www-form-urlencoded':
      schema:
       properties:
          name:
            description: Updated name of the pet
            type: string
          status:
            description: Updated status of the pet
            type: string
       required:
         - status
responses:
  '200':
    description: Pet updated.
    content:
      'application/json': {}
      'application/xml': {}
  '405':
    description: Method Not Allowed
    content:
      'application/json': {}
      'application/xml': {}
security:
- petstore_auth:
  - write:pets
  - read:pets
{
  "name": "Apache 2.0",
  "url": "https://www.apache.org/licenses/LICENSE-2.0.html"
}name: Apache 2.0
url: https://www.apache.org/licenses/LICENSE-2.0.html{
  "url": "https://development.gigantic-server.com/v1",
  "description": "Development server"
}
url: https://development.gigantic-server.com/v1
description: Development server
The following shows how multiple servers can be described, for example, at the OpenAPI Object's servers:

{
  "servers": [
    {
      "url": "https://development.gigantic-server.com/v1",
      "description": "Development server"
    },
    {
      "url": "https://staging.gigantic-server.com/v1",
      "description": "Staging server"
    },
    {
      "url": "https://api.gigantic-server.com/v1",
      "description": "Production server"
    }
  ]
}
servers:
- url: https://development.gigantic-server.com/v1
  description: Development server
- url: https://staging.gigantic-server.com/v1
  description: Staging server
- url: https://api.gigantic-server.com/v1
  description: Production server
The following shows how variables can be used for a server configuration:

{
  "servers": [
    {
      "url": "https://{username}.gigantic-server.com:{port}/{basePath}",
      "description": "The production API server",
      "variables": {
        "username": {
          "default": "demo",
          "description": "this value is assigned by the service provider, in this example `gigantic-server.com`"
        },
        "port": {
          "enum": [
            "8443",
            "443"
          ],
          "default": "8443"
        },
        "basePath": {
          "default": "v2"
        }
      }
    }
  ]
}
servers:
- url: https://{username}.gigantic-server.com:{port}/{basePath}
  description: The production API server
  variables:
    username:
      # note! no enum here means it is an open value
      default: demo
      description: this value is assigned by the service provider, in this example `gigantic-server.com`
    port:
      enum:
        - '8443'
        - '443'
      default: '8443'
    basePath:
      # open meaning there is the opportunity to use special base paths as assigned by the provider, default is `v2`
      default: v2
EADME

License
CommonMark

CommonMark is a rationalized version of Markdown syntax, with a spec and BSD-licensed reference implementations in C and JavaScript.

Try it now!

For more details, see https://commonmark.org.

This repository contains the spec itself, along with tools for running tests against the spec, and for creating HTML and PDF versions of the spec.

The reference implementations live in separate repositories:

https://github.com/commonmark/cmark (C)
https://github.com/commonmark/commonmark.js (JavaScript)
There is a list of third-party libraries in a dozen different languages here.

Running tests against the spec

The spec contains over 500 embedded examples which serve as conformance tests. To run the tests using an executable $PROG:

python3 test/spec_tests.py --program $PROG
If you want to extract the raw test data from the spec without actually running the tests, you can do:

python3 test/spec_tests.py --dump-tests
and you'll get all the tests in JSON format.

JavaScript developers may find it more convenient to use the commonmark-spec npm package, which is published from this repository. It exports an array tests of JSON objects with the format

{
  "markdown": "Foo\nBar\n---\n",
  "html": "<h2>Foo\nBar</h2>\n",
  "section": "Setext headings",
  "number": 65
}
The spec

The source of the spec is spec.txt. This is basically a Markdown file, with code examples written in a shorthand form:

```````````````````````````````` example
Markdown source
.
expected HTML output
````````````````````````````````

> these are two

> blockquotes

> this is a single
>
> blockquote with two paragraphs

pm.variables.has(variableName:String):function → Boolean
Get the value of the Postman variable with the specified name:
pm.variables.get(variableName:String):function → *
Set a local variable with the specified name and value:
pm.variables.set(variableName:String, variableValue:*):function
Return the resolved value of a dynamic variable inside a script using the syntax {{$variableName}}:
pm.variables.replaceIn(variableName:String):function: → *
For example:

const stringWithVars = pm.variables.replaceIn("Hi, my name is {{$randomFirstName}}");
console.log(stringWithVars);
Return an object containing all variables with their values in the current scope. Based on the order of precedence, this will contain variables from multiple scopes.
pm.variables.toObject():function → Object
postman.setNextRequest(requestName:String):Function
Run the specified request after this one (the request ID returned by pm.info.requestId):
postman.setNextRequest(requestId:String):Function
For example:

//script in another request calls:
//pm.environment.set('next', pm.info.requestId)
postman.setNextRequest(pm.environment.get('next'));
Scripting Postman Visualizations

Use pm.visualizer.set to specify a template to display response data in the Postman Visualizer.

pm.visualizer.set(layout:String, data:Object, options:Object):Function
layout required
Handlebars HTML template string
data optional
JSON object that binds to the template and you can access it inside the template string
options optional
Options object for Handlebars.compile()
Example usage:

var template = `<p>{{res.info}}</p>`;
pm.visualizer.set(template, {
    res: pm.response.json()
});
Building response data into Postman Visualizations

Use pm.getData to retrieve response data inside a Postman Visualizer template string.

pm.getData(callback):Function
The callback function accepts two parameters:

error
Any error detail
data
Data passed to the template by pm.visualizer.set
Example usage:

pm.getData(function (error, data) {
  var value = data.res.info;
});
Writing test assertions

pm.test(testName:String, specFunction:Function):Function
You can use pm.test to write test specifications inside either the Pre-request or Tests scripts. Tests include a name and assertion—Postman will output test results as part of the response.

The pm.test method returns the pm object, making the call chainable. The following sample test checks that a response is valid to proceed.

pm.test("response should be okay to process", function () {
  pm.response.to.not.be.error;
  pm.response.to.have.jsonBody('');
  pm.response.to.not.have.jsonBody('error');
});
An optional done callback can be passed to pm.test, to test asynchronous functions.

pm.test('async test', function (done) {
  setTimeout(() => {
    pm.expect(pm.response.code).to.equal(200);
    done();
  }, 1500);
});
Get the total number of tests executed from a specific location in code:
pm.test.index():Function → Number
The pm.expect method allows you to write assertions on your response data, using ChaiJS expect BDD syntax.

pm.expect(assertion:*):Function → Assertion
You can also use pm.response.to.have.* and pm.response.to.be.* to build your assertions.

See Test examples for more assertions.

Using external libraries

require(moduleName:String):function → *
The require method allows you to use the 

> npm install postman-collection --save
Getting Started
In this example snippet we will get started by loading a collection from a file and output the same in console.

var fs = require('fs'), // needed to read JSON file from disk
	Collection = require('postman-collection').Collection,
	myCollection;

// Load a collection to memory from a JSON file on disk (say, sample-collection.json)
myCollection = new Collection(JSON.parse(fs.readFileSync('sample-collection.json').toString()));

// log items at root level of the collection
console.log(myCollection.toJSON());
# Create a folder
$ mkdir actions-runner && cd actions-runner
# Download the latest runner package
$ curl -o actions-runner-linux-arm-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-linux-arm-2.314.1.tar.gz
# Optional: Validate the hash
$ echo "a653dd46dafd47c9a3a6637a18161a1445ac6b9c3f6d6b0305be9e1ee65769af  actions-runner-linux-arm-2.314.1.tar.gz" | shasum -a 256 -c
# Extract the installer
$ tar xzf ./actions-runner-linux-arm-2.314.1.tar.gz
Configure
# Create the runner and start the configuration experience
$ ./config.sh --url https://github.com/grateful345/AGENCY-WEBHOOK --token BHAHZGAPZ7TETPSETRUTYETF7TSAQ
# Last step, run it!
$ ./run.sh
Using your self-hosted runner
# Use this YAML in your workflow file for each job
runs-on: self-hosted
folder permissions and long path restrictions on Windows.

# Create a folder under the drive root
$ mkdir actions-runner; cd actions-runner
# Download the latest runner package
$ Invoke-WebRequest -Uri https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-win-arm64-2.314.1.zip -OutFile actions-runner-win-arm64-2.314.1.zip
# Optional: Validate the hash
$ if((Get-FileHash -Path actions-runner-win-arm64-2.314.1.zip -Algorithm SHA256).Hash.ToUpper() -ne 'acc807696d1dcad6fb45f6038f884185c54c48127445c365e86d03adb164a9e2'.ToUpper()){ throw 'Computed checksum did not match' }
# Extract the installer
$ Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$PWD/actions-runner-win-arm64-2.314.1.zip", "$PWD")
Configure
# Create the runner and start the configuration experience
$ ./config.cmd --url https://github.com/grateful345/AGENCY-WEBHOOK --token BHAHZGAPZ7TETPSETRUTYETF7TSAQ
# Run it!
$ ./run.cmd
Using your self-hosted runner
# Use this YAML in your workflow file for each job
runs-on: self-hosted
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/keys
# Create a folder
$ mkdir actions-runner && cd actions-runner
# Download the latest runner package
$ curl -o actions-runner-osx-arm64-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-osx-arm64-2.314.1.tar.gz
# Optional: Validate the hash
$ echo "e34dab0b4707ad9a9db75f5edf47a804e293af853967a5e0e3b29c8c65f3a004  actions-runner-osx-arm64-2.314.1.tar.gz" | shasum -a 256 -c
# Extract the installer
$ tar xzf ./actions-runner-osx-arm64-2.314.1.tar.gz
Configure
# Create the runner and start the configuration experience
$ ./config.sh --url https://github.com/grateful345/AGENCY-WEBHOOK --token BHAHZGAPZ7TETPSETRUTYETF7TSAQ
# Last step, run it!
$ ./run.sh
Using your self-hosted runner
# Use this YAML in your workflow file for each job
runs-on: self-hosted

{
  "type": "array",
  "items": {
    "title": "Deploy Key",
    "description": "An SSH key granting access to a single repository.",
    "type": "object",
    "properties": {
      "id": {
        "type": "integer"
      },
      "key": {
        "type": "string"
      },
      "url": {
        "type": "string"
      },
      "title": {
        "type": "string"
      },
      "verified": {
        "type": "boolean"
      },
      "created_at": {
        "type": "string"
      },
      "read_only": {
        "type": "boolean"
      },
      "added_by": {
        "type": [
          "string",
          "null"
        ]
      },
      "last_used": {
        "type": [
          "string",
          "null"
        ]
      }
    },
    "required": [
      "id",
      "key",
      "url",
      "title",
      "verified",
      "created_at",
      "read_only"
    ]
  }
}

curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/keys \
  -d '{"title":"octocat@octomac","key":"ssh-rsa AAA...","read_only":true}'

{
  "title": "Deploy Key",
  "description": "An SSH key granting access to a single repository.",
  "type": "object",
  "properties": {
    "id": {
      "type": "integer"
    },
    "key": {
      "type": "string"
    },
    "url": {
      "type": "string"
    },
    "title": {
      "type": "string"
    },
    "verified": {
      "type": "boolean"
    },
    "created_at": {
      "type": "string"
    },
    "read_only": {
      "type": "boolean"
    },
    "added_by": {
      "type": [
        "string",
        "null"
      ]
    },
    "last_used": {
      "type": [
        "string",
        "null"
      ]
    }
  },
  "required": [
    "id",
    "key",
    "url",
    "title",
    "verified",
    "created_at",
    "read_only"
  ]
}

curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/keys/KEY_ID

{
    "image": "mcr.microsoft.com/devcontainers/base:ubuntu"
}
However, [Dockerfiles](https://docs.docker.com/engine/reference/builder/) are a great way to extend images, add additional native OS packages, or make minor edits to the OS image. You can reuse any Dockerfile, but let’s walk through how to create one from scratch.

First, add a file named Dockerfile next to your devcontainer.json. For example:

FROM mcr.microsoft.com/devcontainers/base:ubuntu
# Install the xz-utils package
RUN apt-get update && apt-get install -y xz-utils
Next, remove the image property from devcontainer.json (if it exists) and add the build and dockerfile properties instead:

{
    "build": {
        // Path is relative to the devcontainer.json file.
        "dockerfile": "Dockerfile"
    }
}

YAML
name: Comment when opened
on:
  issues:
    types:
      - opened
jobs:
  comment:
    runs-on: ubuntu-latest
    steps:
      - run: gh issue comment $ISSUE --body "Thank you for opening this issue!"
        env:
          GH_TOKEN: ${{ BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}
          ISSUE: ${{ github.event.issue.html_url }}
You can also execute API calls through GitHub CLI. For example, this workflow first uses the gh api subcommand to query the GraphQL API and parse the result. Then it stores the result in an environment variable that it can access in a later step. In the second step, it uses the gh issue create subcommand to create an issue containing the information from the first step.

YAML
name: Report remaining open issues
on: 
  schedule: 
    # Daily at 8:20 UTC
    - cron: '20 8 * * *'
jobs:
  track_pr:
    runs-on: ubuntu-latest
    steps:
      - run: |
          numOpenIssues="$(gh api graphql -F owner=$OWNER -F name=$REPO -f query='
            query($name: String!, $owner: String!) {
              repository(owner: $Grateful345, name: $keith_Bieszczat) {
                issues(states:OPEN){
                  totalCount
                }
              }
            }
          ' --jq '.data.repository.issues.totalCount')"

          echo 'NUM_OPEN_ISSUES='$numOpenIssues >> $GITHUB_ENV
        env:
          GH_TOKEN: ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}
          OWNER: ${{ github.repository_owner }}
          REPO: ${{ Agency Webhook }}
      - run: |
          gh issue create --title "Issue report" --body "$NUM_OPEN_ISSUES issues remaining" --repo $GITHUB_REPOSITORY
        env:
          GH_TOKEN: ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}

name: Open new issue
on: workflow_dispatch

jobs:
  open-issue:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      issues: write
    steps:
      - run: |
          gh issue --repo ${{ Agency Webhook }} \
            create --title "Issue title" --body "Issue body"
        env:
          GH_TOKEN: ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}
[Example 2: calling the REST API](https://docs.github.com/en/actions/security-guides/automatic-token-authentication#example-2-calling-the-rest-api)

You can use the GITHUB_TOKEN to make authenticated API calls. This example workflow creates an issue using the GitHub REST API:

name: Create issue on commit

on: [ push ]

jobs:
  create_issue:
    runs-on: ubuntu-latest
    permissions:
      issues: write
    steps:
      - name: Create issue using REST API
        run: |
          curl --request POST \
          --url https://api.github.com/repos/${{ github.repository }}/issues \
          --header 'authorization: Bearer ${{  BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24 }}' \
          --header 'content-type: application/json' \
          --data '{
            "title": "Automated issue for commit: ${{ github.sha }}",
            "body": "This issue was automatically created by the GitHub Action workflow **${{ github.workflow }}**. \n\n The commit hash was: _${{ github.sha }}_."
            }' \
          --fail

curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  "https://api.github.com/user/packages?package_type=container"
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/user/docker/conflicts
curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID/restore

curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions/PACKAGE_VERSION_ID
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/versions
  curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME/restore
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/packages/PACKAGE_TYPE/PACKAGE_NAME
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  "https://api.github.com/orgs/ORG/packages?package_type=container"
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer < BHAHZGCJZK3BEVS7IRGZMKDF6USLO / GitHub Runner tokens /  BHAHZGDHHICG3LFF53OICRLF6UR24>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/orgs/ORG/docker/conflicts

Stripe Python Library

pypi Build Status Coverage Status

The Stripe Python library provides convenient access to the Stripe API from applications written in the Python language. It includes a pre-defined set of classes for API resources that initialize themselves dynamically from API responses which makes it compatible with a wide range of versions of the Stripe API.

Documentation

See the Python API docs.

See video demonstrations covering how to use the library.

Installation

You don't need this source code unless you want to modify the package. If you just want to use the package, just run:

pip install --upgrade stripe
Install from source with:

python setup.py install
Requirements

Python 3.6+ (PyPy supported)
Python 2.7 deprecation

The Python Software Foundation (PSF) community announced the end of support of Python 2 on 01 January 2020. Starting with version 6.0.0 Stripe SDK Python packages will no longer support Python 2.7. To continue to get new features and security updates, please make sure to update your Python runtime to Python 3.6+.

The last version of the Stripe SDK that supports Python 2.7 is 5.5.0.

Usage

The library needs to be configured with your account's secret key which is available in your Stripe Dashboard. Set stripe.api_key to its value:

from stripe import StripeClient

client = StripeClient("sk_test_...")

# list customers
customers = client.customers.list()

# print the first customer's email
print(customers.data[0].email)

# retrieve specific Customer
customer = client.customers.retrieve("cus_123456789")

# print that customer's email
print(customer.email)
Handling exceptions

Unsuccessful requests raise exceptions. The class of the exception will reflect the sort of error that occurred. Please see the Api Reference for a description of the error classes you should handle, and for information on how to inspect these errors.

Per-request Configuration

Configure individual requests with the options argument. For example, you can make requests with a specific Stripe Version or as a connected account:

from stripe import StripeClient

client = StripeClient("sk_test_...")

# list customers
client.customers.list(
    options={
        "api_key": "sk_test_...",
        "stripe_account": "acct_...",
        "stripe_version": "2019-02-19",
    }
)

# retrieve single customer
client.customers.retrieve(
    "cus_123456789",
    options={
        "api_key": "sk_test_...",
        "stripe_account": "acct_...",
        "stripe_version": "2019-02-19",
    }
)
Configuring an HTTP Client

You can configure your StripeClient to use urlfetch, requests, pycurl, or urllib2 with the http_client option:

client = StripeClient("sk_test_...", http_client=stripe.UrlFetchClient())
client = StripeClient("sk_test_...", http_client=stripe.RequestsClient())
client = StripeClient("sk_test_...", http_client=stripe.PycurlClient())
client = StripeClient("sk_test_...", http_client=stripe.Urllib2Client())
Without a configured client, by default the library will attempt to load libraries in the order above (i.e. urlfetch is preferred with urllib2 used as a last resort). We usually recommend that people use requests.

Configuring a Proxy

A proxy can be configured with the proxy client option:

client = StripeClient("sk_test_...", proxy="https://user:pass@example.com:1234")
Configuring Automatic Retries

You can enable automatic retries on requests that fail due to a transient problem by configuring the maximum number of retries:

client = StripeClient("sk_test_...", max_network_retries=2)
Various errors can trigger a retry, like a connection error or a timeout, and also certain API responses like HTTP status 409 Conflict.

Idempotency keys are automatically generated and added to requests, when not given, to guarantee that retries are safe.

Logging

The library can be configured to emit logging that will give you better insight into what it's doing. The info logging level is usually most appropriate for production use, but debug is also available for more verbosity.

There are a few options for enabling it:

Set the environment variable STRIPE_LOG to the value debug or info

$ export STRIPE_LOG=debug
Set stripe.log:

import stripe
stripe.log = 'debug'
Enable it through Python's logging module:

import logging
logging.basicConfig()
logging.getLogger('stripe').setLevel(logging.DEBUG)
Accessing response code and headers

You can access the HTTP response code and headers using the last_response property of the returned resource.

customer = client.customers.retrieve(
    "cus_123456789"
)

print(customer.last_response.code)
print(customer.last_response.headers)
Writing a Plugin

If you're writing a plugin that uses the library, we'd appreciate it if you identified using stripe.set_app_info():

stripe.set_app_info("MyAwesomePlugin", version="1.2.34", url="https://myawesomeplugin.info")
This information is passed along when the library makes calls to the Stripe API.

Telemetry

By default, the library sends telemetry to Stripe regarding request latency and feature usage. These numbers help Stripe improve the overall latency of its API for all users, and improve popular features.

You can disable this behavior if you prefer:

stripe.enable_telemetry = False
Types

In v7.1.0 and newer, the library includes type annotations. See the wiki for a detailed guide.

Please note that some annotations use features that were only fairly recently accepted, such as Unpack[TypedDict] that was accepted in January 2023. We have tested that these types are recognized properly by Pyright. Support for Unpack in MyPy is still experimental, but appears to degrade gracefully. Please report an issue if there is anything we can do to improve the types for your type checker of choice.

Types and the Versioning Policy

We release type changes in minor releases. While stripe-python follows semantic versioning, our semantic versions describe the runtime behavior of the library alone. Our type annotations are not reflected in the semantic version. That is, upgrading to a new minor version of stripe-python might result in your type checker producing a type error that it didn't before. You can use a ~=x.x or x.x.* version specifier in your requirements.txt to constrain pip to a certain minor range of stripe-python.

Types and API Versions

The types describe the Stripe API version that was the latest at the time of release. This is the version that your library sends by default. If you are overriding stripe.api_version / stripe_version on the StripeClient, or using a webhook endpoint tied to an older version, be aware that the data you see at runtime may not match the types.

Beta SDKs

Stripe has features in the beta phase that can be accessed via the beta version of this package. We would love for you to try these and share feedback with us before these features reach the stable phase. To install a beta version use pip install with the exact version you'd like to use:

pip install stripe==v8.6.0b1
Note There can be breaking changes between beta versions. Therefore we recommend pinning the package version to a specific beta version in your requirements file or setup.py. This way you can install the same version each time without breaking changes unless you are intentionally looking for the latest beta version.
We highly recommend keeping an eye on when the beta feature you are interested in goes from beta to stable so that you can move from using a beta version of the SDK to the stable version.

If your beta feature requires a Stripe-Version header to be sent, set the stripe.api_version field using the stripe.add_beta_version function:

stripe.add_beta_version("feature_beta", "v3")
Support

New features and bug fixes are released on the latest major version of the Stripe Python library. If you are on an older major version, we recommend that you upgrade to the latest in order to use the new features and bug fixes including those for security vulnerabilities. Older major versions of the package will continue to be available for use, but will not be receiving any updates.

Development

The test suite depends on stripe-mock, so make sure to fetch and run it from a background terminal (stripe-mock's README also contains instructions for installing via Homebrew and other methods):

go install github.com/stripe/stripe-mock@latest
stripe-mock
Run the following command to set up the development virtualenv:

make
Run all tests on all supported Python versions:

make test
Run all tests for a specific Python version (modify -e according to your Python target):

TOX_ARGS="-e py37" make test
Run all tests in a single file:

TOX_ARGS="-e py37 -- tests/api_resources/abstract/test_updateable_api_resource.py" make test
Run a single test suite:

TOX_ARGS="-e py37 -- tests/api_resources/abstract/test_updateable_api_resource.py::TestUpdateableAPIResource" make test
Run a single test:

TOX_ARGS="-e py37 -- tests/api_resources/abstract/test_updateable_api_resource.py::TestUpdateableAPIResource::test_save" make test
Run the linter with:

make lint
The library uses Black for code formatting. Code must be formatted with Black before PRs are submitted, otherwise CI will fail. Run the formatter with:

make fmt
