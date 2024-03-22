From 5213814de2537a3ea92b216ee8ed29c78f9503be Mon Sep 17 00:00:00 2001
From: keith T bieszczat sr <163609752+grateful345@users.noreply.github.com>
Date: Fri, 22 Mar 2024 02:15:28 -0500
Subject: [PATCH] Update Trello.md

Trello
---
 Trello.md | 502 ++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 502 insertions(+)

diff --git a/Trello.md b/Trello.md
index 209fc9f..02c2ba4 100644
--- a/Trello.md
+++ b/Trello.md
@@ -1,6 +1,508 @@
 Trello Api token:
 ATATT3xFfGF0aXRYQM0Q95lcoWqsYEwV4Xo_tqQjaXBJ1xtP-NT1tGoR9zMoJ4OfhAFF8GMncjTZJW2Vn0fKx2hQslfTTc-dSzyik4NitTMMx9IPRrj_fN5aTrND167SHU4Wv3enJnpjETXFjSvg3KGmNdVNqFknmc0VkLnP-8ZdTik6atWQJxg=D74F7DC5
 
+curl https://api.trello.com/1/actions/592f11060f95a3d3d46a987a
+{
+  "id": "592f11060f95a3d3d46a987a",
+  "idMemberCreator": "5191197f9433cf5507006338",
+  "data": {
+    "list": {
+      "name": "Professional",
+      "id": "54a17e9db559f0356ce022e4"
+    },
+    "board": {
+      "shortLink": "BdarzfKF",
+      "name": "Life Goals",
+      "id": "54a17d76d4a5072e3931736b"
+    },
+    "card": {
+      "shortLink": "gplJv6dx",
+      "idShort": 2,
+      "name": "Increase revenue by 10%",
+      "id": "54a1844d304d9736e54d2546",
+      "due": "2017-12-12T17:00:00.000Z"
+    },
+    "old": {
+      "due": "2017-05-01T16:00:00.000Z"
+    }
+  },
+  "type": "updateCard",
+  "date": "2017-05-31T18:52:54.933Z",
+  "memberCreator": {
+    "id": "5191197f9433cf5507006338",
+    "avatarHash": "ae0fde383cc2a195c053f1ad42c02022",
+    "fullName": "Brian Cervino",
+    "initials": "BC",
+    "username": "brian"
+  },
+  "display": {
+    "translationKey": "action_changed_a_due_date",
+    "entities": {
+      "card": {
+        "type": "card",
+        "due": "2017-12-12T17:00:00.000Z",
+        "id": "54a1844d304d9736e54d2546",
+        "shortLink": "gplJv6dx",
+        "text": "Increase revenue by 10%"
+      },
+      "date": {
+        "type": "date",
+        "date": "2017-12-12T17:00:00.000Z"
+      },
+      "memberCreator": {
+        "type": "member",
+        "id": "5191197f9433cf5507006338",
+        "username": "brian",
+        "text": "Brian Cervino"
+      }
+    }
+  }
+}
+curl https://api.trello.com/1/cards/bxK53hfo/attachments/602a8501ecff9a3942b922ec
+{
+  "id": "602a8501ecff9a3942b922ec",
+  "bytes": 61114,
+  "date": "2021-02-15T14:28:17.202Z",
+  "edgeColor": "#5c5c5c",
+  "idMember": "5fa06c67bb60727b6ada0b43",
+  "isUpload": true,
+  "mimeType": "image/png",
+  "name": "Screenshot 2021-02-09 at 16.35.29.png",
+  "previews": [
+    {
+      "id": "602a8501ecff9a3942b922f7",
+      "_id": "602a8501ecff9a3942b922f7",
+      "scaled": false,
+      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922f7/download",
+      "bytes": 2397,
+      "height": 50,
+      "width": 70
+    },
+    {
+      "id": "602a8501ecff9a3942b922f8",
+      "_id": "602a8501ecff9a3942b922f8",
+      "scaled": false,
+      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922f8/download",
+      "bytes": 10977,
+      "height": 150,
+      "width": 250
+    },
+    {
+      "id": "602a8501ecff9a3942b922f9",
+      "_id": "602a8501ecff9a3942b922f9",
+      "scaled": true,
+      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922f9/download",
+      "bytes": 10115,
+      "height": 145,
+      "width": 150
+    },
+    {
+      "id": "602a8501ecff9a3942b922fa",
+      "_id": "602a8501ecff9a3942b922fa",
+      "scaled": true,
+      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922fa/download",
+      "bytes": 25965,
+      "height": 291,
+      "width": 300
+    },
+    {
+      "id": "602a8501ecff9a3942b922fb",
+      "_id": "602a8501ecff9a3942b922fb",
+      "scaled": true,
+      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922fb/download",
+      "bytes": 40886,
+      "height": 512,
+      "width": 528
+    },
+    {
+      "id": "602a8501ecff9a3942b922fc",
+      "_id": "602a8501ecff9a3942b922fc",
+      "scaled": true,
+      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922fc/download",
+      "bytes": 61114,
+      "height": 512,
+      "width": 528
+    }
+  ],
+  "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/download/Screenshot_2021-02-09_at_16.35.29.png",
+  "pos": 16384,
+  "fileName": "Screenshot_2021-02-09_at_16.35.29.png"
+}
+curl https://api.trello.com/1/boards/5612e4f91b25c15e873722b8?fields=all
+{
+  "id": "5612e4f91b25c15e873722b8",
+  "name": "Employee Manual",
+  "desc": "",
+  "descData": null,
+  "closed": false,
+  "idOrganization": "54b58957112602c9a0be7aa3",
+  "idMemberCreator": "53baf533e697a982248cd73f",
+  "invited": false,
+  "limits": {
+    "attachments": {
+      "perBoard": {
+        "status": "ok",
+        "disableAt": 34200,
+        "warnAt": 32400
+      }
+    },
+    "boards": {
+      "totalMembersPerBoard": {
+        "status": "ok",
+        "disableAt": 1520,
+        "warnAt": 1440
+      }
+    },
+    "cards": {
+      "openPerBoard": {
+        "status": "ok",
+        "disableAt": 5000,
+        "warnAt": 4500
+      },
+      "totalPerBoard": {
+        "status": "ok",
+        "disableAt": 2000000,
+        "warnAt": 1800000
+      }
+    },
+    "checklists": {
+      "perBoard": {
+        "status": "ok",
+        "disableAt": 2000000,
+        "warnAt": 1800000
+      }
+    },
+    "customFields": {
+      "perBoard": {
+        "status": "ok",
+        "disableAt": 48,
+        "warnAt": 45
+      }
+    },
+    "labels": {
+      "perBoard": {
+        "status": "ok",
+        "disableAt": 950,
+        "warnAt": 900
+      }
+    },
+    "lists": {
+      "openPerBoard": {
+        "status": "ok",
+        "disableAt": 475,
+        "warnAt": 450
+      },
+      "totalPerBoard": {
+        "status": "ok",
+        "disableAt": 2850,
+        "warnAt": 2700
+      }
+    }
+  },
+  "memberships": [
+    {
+      "id": "5612e4fb1b25c15e8737234b",
+      "idMember": "53baf533e697a982248cd73f",
+      "memberType": "admin",
+      "unconfirmed": false
+    },
+    {
+      "id": "5925e4fc63096260c349cbd4",
+      "idMember": "53cd82cd7ed746db278c4f32",
+      "memberType": "normal",
+      "unconfirmed": false
+    }
+  ],
+  "pinned": false,
+  "starred": false,
+  "url": "https://trello.com/b/HbTEX5hb/employee-manual",
+  "prefs": {
+    "permissionLevel": "public",
+    "voting": "disabled",
+    "comments": "members",
+    "invitations": "members",
+    "selfJoin": true,
+    "cardCovers": true,
+    "cardAging": "regular",
+    "calendarFeedEnabled": false,
+    "background": "5925b78fa1bd45e1bfb835da",
+    "backgroundImage": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/2560x1707/f3c8b6101072d80565d9b6368f05b19d/photo-1495571758719-6ec1e876d6ae",
+    "backgroundImageScaled": [
+      {
+        "width": 140,
+        "height": 100,
+        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/140x100/5afcd242d52da7ad4827966d8c896c00/photo-1495571758719-6ec1e876d6ae.jpg"
+      },
+      {
+        "width": 256,
+        "height": 192,
+        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/256x192/d297510e553abc340fb0de3570445f03/photo-1495571758719-6ec1e876d6ae.jpg"
+      },
+      {
+        "width": 480,
+        "height": 480,
+        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/480x480/08b5996b0a87a0f3dd80af488d99194a/photo-1495571758719-6ec1e876d6ae.jpg"
+      },
+      {
+        "width": 960,
+        "height": 960,
+        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/960x960/7cb60ad23bdee1ca45a7c5e4e0c07968/photo-1495571758719-6ec1e876d6ae.jpg"
+      },
+      {
+        "width": 1024,
+        "height": 1024,
+        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/1024x1024/dca79e47ce10cd2c985dc4ba61abd9cc/photo-1495571758719-6ec1e876d6ae.jpg"
+      },
+      {
+        "width": 2048,
+        "height": 2048,
+        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/2048x2048/b5a88d70569d9ded2af259e8d332c346/photo-1495571758719-6ec1e876d6ae.jpg"
+      },
+      {
+        "width": 1280,
+        "height": 1280,
+        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/1280x1280/c9ae077543d6c41ea2d48d84fdc12484/photo-1495571758719-6ec1e876d6ae.jpg"
+      },
+      {
+        "width": 1920,
+        "height": 1920,
+        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/1920x1920/cc85a9a12195863a1ff2193b5bb3a651/photo-1495571758719-6ec1e876d6ae.jpg"
+      },
+      {
+        "width": 2560,
+        "height": 1600,
+        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/2560x1600/de59d9e742f2de51d4284c6fd7c07f5d/photo-1495571758719-6ec1e876d6ae.jpg"
+      },
+      {
+        "width": 2560,
+        "height": 1707,
+        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/2560x1707/f3c8b6101072d80565d9b6368f05b19d/photo-1495571758719-6ec1e876d6ae"
+      }
+    ],
+    "backgroundTile": false,
+    "backgroundBrightness": "light",
+    "backgroundBottomColor": "#332b09",
+    "backgroundTopColor": "#d3c4a9",
+    "canBePublic": false,
+    "canBeOrg": false,
+    "canBePrivate": false,
+    "canInvite": true
+  },
+  "invitations": [],
+  "shortLink": "HbTEX5hb",
+  "subscribed": false,
+  "labelNames": {
+    "green": "",
+    "yellow": "good to go",
+    "orange": "",
+    "red": "",
+    "purple": "",
+    "blue": "",
+    "sky": "",
+    "lime": "",
+    "pink": "",
+    "black": ""
+  },
+  "powerUps": [],
+  "dateLastActivity": "2016-01-07T21:24:47.855Z",
+  "dateLastView": "2018-03-12T14:15:20.234Z",
+  "shortUrl": "https://trello.com/b/HbTEX5hb",
+  "idTags": [],
+  "datePluginDisable": null
+}
+
+curl https://api.trello.com/1/cards/560bf4dd7139286471dc009c?fields=all
+{
+  "id": "560bf4dd7139286471dc009c",
+  "badges": {
+    "votes": 0,
+    "viewingMemberVoted": false,
+    "subscribed": true,
+    "fogbugz": "",
+    "checkItems": 0,
+    "checkItemsChecked": 0,
+    "comments": 0,
+    "attachments": 2,
+    "description": false,
+    "due": null,
+    "dueComplete": false
+  },
+  "checkItemStates": [
+
+  ],
+  "closed": false,
+  "dueComplete": false,
+  "dateLastActivity": "2017-06-26T17:39:49.583Z",
+  "desc": "",
+  "descData": null,
+  "due": null,
+  "email": null,
+  "idBoard": "560bf4298b3dda300c18d09c",
+  "idChecklists": [
+
+  ],
+  "idList": "560bf44ea68b16bd0fc2a9a9",
+  "idMembers": [
+    "556c8537a1928ba745504dd8"
+  ],
+  "idMembersVoted": [
+
+  ],
+  "idShort": 9,
+  "idAttachmentCover": "5944a06460ed0bee471ad8e0",
+  "manualCoverAttachment": false,
+  "labels": [
+    {
+      "id": "560bf42919ad3a5dc29f33c5",
+      "idBoard": "560bf4298b3dda300c18d09c",
+      "name": "Visited",
+      "color": "green"
+    }
+  ],
+  "idLabels": [
+    "560bf42919ad3a5dc29f33c5"
+  ],
+  "name": "Grand Canyon National Park",
+  "pos": 16384,
+  "shortLink": "nqPiDKmw",
+  "shortUrl": "https://trello.com/c/nqPiDKmw",
+  "subscribed": true,
+  "url": "https://trello.com/c/nqPiDKmw/9-grand-canyon-national-park",
+  "address": "55 Broadway\nSan Francisco CA 94111\nUnited States",
+  "locationName": "55 Broadway, NY 10280",
+  "coordinates": {
+    "latitude": 37.7986712,
+    "longitude": -122.3991514
+  }
+}
+curl https://api.trello.com/1/member/592f11060f95a3d3d46a987a
+
+curl https://api.trello.com/1/cards/F2C06Ly8/stickers/602a9a7a533aa85b97624292
+{
+  "id": "602a9a7a533aa85b97624292",
+  "top": 0,
+  "left": 56.62370816929134,
+  "zIndex": 1,
+  "rotate": -6,
+  "image": "check",
+  "imageUrl": "https://d2k1ftgv7pobq7.cloudfront.net/images/stickers/check.png",
+  "imageScaled": []
+}
+
+curl https://api.trello.com/1/boards/552595baa7b650edb7a0f8ff/?fields=limits
+
+{
+  "id": "552595baa7b650edb7a0f8ff",
+  "limits": {
+    "boards": {
+      "totalMembersPerBoard": {
+        "status": "ok",
+        "disableAt": 1520,
+        "warnAt": 1440
+      }
+    },
+    "cards": {
+      "openPerBoard": {
+        "status": "ok",
+        "disableAt": 5000,
+        "warnAt": 4500
+      },
+      "totalPerBoard": {
+        "status": "ok",
+        "disableAt": 2000000,
+        "warnAt": 1800000
+      }
+    },
+    "checklists": {
+      "perBoard": {
+        "status": "ok",
+        "disableAt": 15200,
+        "warnAt": 14400
+      }
+    },
+    "labels": {
+      "perBoard": {
+        "status": "ok",
+        "disableAt": 950,
+        "warnAt": 900
+      }
+    },
+    "lists": {
+      "openPerBoard": {
+        "status": "ok",
+        "disableAt": 475,
+        "warnAt": 450
+      },
+      "totalPerBoard": {
+        "status": "ok",
+        "disableAt": 2850,
+        "warnAt": 2700
+      }
+    }
+  }
+}
+curl https://trello.com/1/boards/552595baa7b650edb7a0f8ff/cards/?fields=limits&limit=1
+
+trello develop board id:
+4d5ea62fd76aa1136000000c
+Taking the first 8 characters, we get:
+1
+4d5ea62f
+Converted to a decimal from hexadecimal, the timestamp is:
+1
+1298048559
+
+=(((HEX2DEC(Left(A1,8))/60)/60)/24)+DATE(1970,1,1)
+idBoard = "4d5ea62fd76aa1136000000c";
+new Date(1000*parseInt(idBoard.substring(0,8),16));
+Python Example
+1
+2
+3
+4
+5
+import pytz
+from datetime import datetime
+id_board = "4d5ea62fd76aa1136000000c"
+creation_time = datetime.fromtimestamp(int(id_board[0:8],16))
+utc_creation_time = pytz.utc.localize(creation_time)
+R Example
+1
+2
+3
+cardID = "4d5ea62fd76aa1136000000c"
+timestamp = strtoi(strtrim(cardID, 8), 16L)
+dateCrceated = as.POSIXct(timestamp, origin = "1970-01-01")
+PHP Example
+1
+2
+3
+4
+5
+<?php
+$cardID = '4d5ea62fd76aa1136000000c';
+$createdDate = date('r', hexdec( substr( $cardID , 0, 8 ) ) );
+echo $createdDate;
+?>
+
+newObjectId = ObjectId()
+
+ObjectId("507f1f77bcf86cd799439011")
+ObjectId("507f191e810c19729de860ea").toString()
+507f191e810c19729de860ea
+newObjectId = ObjectId(32)
+ObjectId("00000020f51bb4362eee2a4d")
+newObjectId = ObjectId("507f191e810c19729de860ea")
+
+
+
+
+
+
+
+
+
+
 curl --request GET \
   --url 'https://your-domain.atlassian.net/configuration/retention' \
   --header 'Accept: application/json'
