Trello Api token:
ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7

curl https://api.trello.com/1/actions/592f11060f95a3d3d46a987a
{
  "id": "592f11060f95a3d3d46a987a",
  "idMemberCreator": "5191197f9433cf5507006338",
  "data": {
    "list": {
      "name": "Professional",
      "id": "54a17e9db559f0356ce022e4"
    },
    "board": {
      "shortLink": "BdarzfKF",
      "name": "Life Goals",
      "id": "54a17d76d4a5072e3931736b"
    },
    "card": {
      "shortLink": "gplJv6dx",
      "idShort": 2,
      "name": "Increase revenue by 10%",
      "id": "54a1844d304d9736e54d2546",
      "due": "2017-12-12T17:00:00.000Z"
    },
    "old": {
      "due": "2017-05-01T16:00:00.000Z"
    }
  },
  "type": "updateCard",
  "date": "2017-05-31T18:52:54.933Z",
  "memberCreator": {
    "id": "5191197f9433cf5507006338",
    "avatarHash": "ae0fde383cc2a195c053f1ad42c02022",
    "fullName": "Brian Cervino",
    "initials": "BC",
    "username": "brian"
  },
  "display": {
    "translationKey": "action_changed_a_due_date",
    "entities": {
      "card": {
        "type": "card",
        "due": "2017-12-12T17:00:00.000Z",
        "id": "54a1844d304d9736e54d2546",
        "shortLink": "gplJv6dx",
        "text": "Increase revenue by 10%"
      },
      "date": {
        "type": "date",
        "date": "2017-12-12T17:00:00.000Z"
      },
      "memberCreator": {
        "type": "member",
        "id": "5191197f9433cf5507006338",
        "username": "brian",
        "text": "Brian Cervino"
      }
    }
  }
}
curl https://api.trello.com/1/cards/bxK53hfo/attachments/602a8501ecff9a3942b922ec
{
  "id": "602a8501ecff9a3942b922ec",
  "bytes": 61114,
  "date": "2021-02-15T14:28:17.202Z",
  "edgeColor": "#5c5c5c",
  "idMember": "5fa06c67bb60727b6ada0b43",
  "isUpload": true,
  "mimeType": "image/png",
  "name": "Screenshot 2021-02-09 at 16.35.29.png",
  "previews": [
    {
      "id": "602a8501ecff9a3942b922f7",
      "_id": "602a8501ecff9a3942b922f7",
      "scaled": false,
      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922f7/download",
      "bytes": 2397,
      "height": 50,
      "width": 70
    },
    {
      "id": "602a8501ecff9a3942b922f8",
      "_id": "602a8501ecff9a3942b922f8",
      "scaled": false,
      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922f8/download",
      "bytes": 10977,
      "height": 150,
      "width": 250
    },
    {
      "id": "602a8501ecff9a3942b922f9",
      "_id": "602a8501ecff9a3942b922f9",
      "scaled": true,
      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922f9/download",
      "bytes": 10115,
      "height": 145,
      "width": 150
    },
    {
      "id": "602a8501ecff9a3942b922fa",
      "_id": "602a8501ecff9a3942b922fa",
      "scaled": true,
      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922fa/download",
      "bytes": 25965,
      "height": 291,
      "width": 300
    },
    {
      "id": "602a8501ecff9a3942b922fb",
      "_id": "602a8501ecff9a3942b922fb",
      "scaled": true,
      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922fb/download",
      "bytes": 40886,
      "height": 512,
      "width": 528
    },
    {
      "id": "602a8501ecff9a3942b922fc",
      "_id": "602a8501ecff9a3942b922fc",
      "scaled": true,
      "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/previews/602a8501ecff9a3942b922fc/download",
      "bytes": 61114,
      "height": 512,
      "width": 528
    }
  ],
  "url": "https://trello.com/1/cards/5fc7d887b4bc7b1039678af6/attachments/602a8501ecff9a3942b922ec/download/Screenshot_2021-02-09_at_16.35.29.png",
  "pos": 16384,
  "fileName": "Screenshot_2021-02-09_at_16.35.29.png"
}
curl https://api.trello.com/1/boards/5612e4f91b25c15e873722b8?fields=all
{
  "id": "5612e4f91b25c15e873722b8",
  "name": "Employee Manual",
  "desc": "",
  "descData": null,
  "closed": false,
  "idOrganization": "54b58957112602c9a0be7aa3",
  "idMemberCreator": "53baf533e697a982248cd73f",
  "invited": false,
  "limits": {
    "attachments": {
      "perBoard": {
        "status": "ok",
        "disableAt": 34200,
        "warnAt": 32400
      }
    },
    "boards": {
      "totalMembersPerBoard": {
        "status": "ok",
        "disableAt": 1520,
        "warnAt": 1440
      }
    },
    "cards": {
      "openPerBoard": {
        "status": "ok",
        "disableAt": 5000,
        "warnAt": 4500
      },
      "totalPerBoard": {
        "status": "ok",
        "disableAt": 2000000,
        "warnAt": 1800000
      }
    },
    "checklists": {
      "perBoard": {
        "status": "ok",
        "disableAt": 2000000,
        "warnAt": 1800000
      }
    },
    "customFields": {
      "perBoard": {
        "status": "ok",
        "disableAt": 48,
        "warnAt": 45
      }
    },
    "labels": {
      "perBoard": {
        "status": "ok",
        "disableAt": 950,
        "warnAt": 900
      }
    },
    "lists": {
      "openPerBoard": {
        "status": "ok",
        "disableAt": 475,
        "warnAt": 450
      },
      "totalPerBoard": {
        "status": "ok",
        "disableAt": 2850,
        "warnAt": 2700
      }
    }
  },
  "memberships": [
    {
      "id": "5612e4fb1b25c15e8737234b",
      "idMember": "53baf533e697a982248cd73f",
      "memberType": "admin",
      "unconfirmed": false
    },
    {
      "id": "5925e4fc63096260c349cbd4",
      "idMember": "53cd82cd7ed746db278c4f32",
      "memberType": "normal",
      "unconfirmed": false
    }
  ],
  "pinned": false,
  "starred": false,
  "url": "https://trello.com/b/HbTEX5hb/employee-manual",
  "prefs": {
    "permissionLevel": "public",
    "voting": "disabled",
    "comments": "members",
    "invitations": "members",
    "selfJoin": true,
    "cardCovers": true,
    "cardAging": "regular",
    "calendarFeedEnabled": false,
    "background": "5925b78fa1bd45e1bfb835da",
    "backgroundImage": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/2560x1707/f3c8b6101072d80565d9b6368f05b19d/photo-1495571758719-6ec1e876d6ae",
    "backgroundImageScaled": [
      {
        "width": 140,
        "height": 100,
        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/140x100/5afcd242d52da7ad4827966d8c896c00/photo-1495571758719-6ec1e876d6ae.jpg"
      },
      {
        "width": 256,
        "height": 192,
        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/256x192/d297510e553abc340fb0de3570445f03/photo-1495571758719-6ec1e876d6ae.jpg"
      },
      {
        "width": 480,
        "height": 480,
        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/480x480/08b5996b0a87a0f3dd80af488d99194a/photo-1495571758719-6ec1e876d6ae.jpg"
      },
      {
        "width": 960,
        "height": 960,
        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/960x960/7cb60ad23bdee1ca45a7c5e4e0c07968/photo-1495571758719-6ec1e876d6ae.jpg"
      },
      {
        "width": 1024,
        "height": 1024,
        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/1024x1024/dca79e47ce10cd2c985dc4ba61abd9cc/photo-1495571758719-6ec1e876d6ae.jpg"
      },
      {
        "width": 2048,
        "height": 2048,
        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/2048x2048/b5a88d70569d9ded2af259e8d332c346/photo-1495571758719-6ec1e876d6ae.jpg"
      },
      {
        "width": 1280,
        "height": 1280,
        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/1280x1280/c9ae077543d6c41ea2d48d84fdc12484/photo-1495571758719-6ec1e876d6ae.jpg"
      },
      {
        "width": 1920,
        "height": 1920,
        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/1920x1920/cc85a9a12195863a1ff2193b5bb3a651/photo-1495571758719-6ec1e876d6ae.jpg"
      },
      {
        "width": 2560,
        "height": 1600,
        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/2560x1600/de59d9e742f2de51d4284c6fd7c07f5d/photo-1495571758719-6ec1e876d6ae.jpg"
      },
      {
        "width": 2560,
        "height": 1707,
        "url": "https://trello-backgrounds.s3.amazonaws.com/SharedBackground/2560x1707/f3c8b6101072d80565d9b6368f05b19d/photo-1495571758719-6ec1e876d6ae"
      }
    ],
    "backgroundTile": false,
    "backgroundBrightness": "light",
    "backgroundBottomColor": "#332b09",
    "backgroundTopColor": "#d3c4a9",
    "canBePublic": false,
    "canBeOrg": false,
    "canBePrivate": false,
    "canInvite": true
  },
  "invitations": [],
  "shortLink": "HbTEX5hb",
  "subscribed": false,
  "labelNames": {
    "green": "",
    "yellow": "good to go",
    "orange": "",
    "red": "",
    "purple": "",
    "blue": "",
    "sky": "",
    "lime": "",
    "pink": "",
    "black": ""
  },
  "powerUps": [],
  "dateLastActivity": "2016-01-07T21:24:47.855Z",
  "dateLastView": "2018-03-12T14:15:20.234Z",
  "shortUrl": "https://trello.com/b/HbTEX5hb",
  "idTags": [],
  "datePluginDisable": null
}

curl https://api.trello.com/1/cards/560bf4dd7139286471dc009c?fields=all
{
  "id": "560bf4dd7139286471dc009c",
  "badges": {
    "votes": 0,
    "viewingMemberVoted": false,
    "subscribed": true,
    "fogbugz": "",
    "checkItems": 0,
    "checkItemsChecked": 0,
    "comments": 0,
    "attachments": 2,
    "description": false,
    "due": null,
    "dueComplete": false
  },
  "checkItemStates": [

  ],
  "closed": false,
  "dueComplete": false,
  "dateLastActivity": "2017-06-26T17:39:49.583Z",
  "desc": "",
  "descData": null,
  "due": null,
  "email": null,
  "idBoard": "560bf4298b3dda300c18d09c",
  "idChecklists": [

  ],
  "idList": "560bf44ea68b16bd0fc2a9a9",
  "idMembers": [
    "556c8537a1928ba745504dd8"
  ],
  "idMembersVoted": [

  ],
  "idShort": 9,
  "idAttachmentCover": "5944a06460ed0bee471ad8e0",
  "manualCoverAttachment": false,
  "labels": [
    {
      "id": "560bf42919ad3a5dc29f33c5",
      "idBoard": "560bf4298b3dda300c18d09c",
      "name": "Visited",
      "color": "green"
    }
  ],
  "idLabels": [
    "560bf42919ad3a5dc29f33c5"
  ],
  "name": "Grand Canyon National Park",
  "pos": 16384,
  "shortLink": "nqPiDKmw",
  "shortUrl": "https://trello.com/c/nqPiDKmw",
  "subscribed": true,
  "url": "https://trello.com/c/nqPiDKmw/9-grand-canyon-national-park",
  "address": "55 Broadway\nSan Francisco CA 94111\nUnited States",
  "locationName": "55 Broadway, NY 10280",
  "coordinates": {
    "latitude": 37.7986712,
    "longitude": -122.3991514
  }
}
curl https://api.trello.com/1/member/592f11060f95a3d3d46a987a

curl https://api.trello.com/1/cards/F2C06Ly8/stickers/602a9a7a533aa85b97624292
{
  "id": "602a9a7a533aa85b97624292",
  "top": 0,
  "left": 56.62370816929134,
  "zIndex": 1,
  "rotate": -6,
  "image": "check",
  "imageUrl": "https://d2k1ftgv7pobq7.cloudfront.net/images/stickers/check.png",
  "imageScaled": []
}

curl https://api.trello.com/1/boards/552595baa7b650edb7a0f8ff/?fields=limits

{
  "id": "552595baa7b650edb7a0f8ff",
  "limits": {
    "boards": {
      "totalMembersPerBoard": {
        "status": "ok",
        "disableAt": 1520,
        "warnAt": 1440
      }
    },
    "cards": {
      "openPerBoard": {
        "status": "ok",
        "disableAt": 5000,
        "warnAt": 4500
      },
      "totalPerBoard": {
        "status": "ok",
        "disableAt": 2000000,
        "warnAt": 1800000
      }
    },
    "checklists": {
      "perBoard": {
        "status": "ok",
        "disableAt": 15200,
        "warnAt": 14400
      }
    },
    "labels": {
      "perBoard": {
        "status": "ok",
        "disableAt": 950,
        "warnAt": 900
      }
    },
    "lists": {
      "openPerBoard": {
        "status": "ok",
        "disableAt": 475,
        "warnAt": 450
      },
      "totalPerBoard": {
        "status": "ok",
        "disableAt": 2850,
        "warnAt": 2700
      }
    }
  }
}
curl https://trello.com/1/boards/552595baa7b650edb7a0f8ff/cards/?fields=limits&limit=1

trello develop board id:
4d5ea62fd76aa1136000000c
Taking the first 8 characters, we get:
1
4d5ea62f
Converted to a decimal from hexadecimal, the timestamp is:
1
1298048559

=(((HEX2DEC(Left(A1,8))/60)/60)/24)+DATE(1970,1,1)
idBoard = "4d5ea62fd76aa1136000000c";
new Date(1000*parseInt(idBoard.substring(0,8),16));
Python Example
1
2
3
4
5
import pytz
from datetime import datetime
id_board = "4d5ea62fd76aa1136000000c"
creation_time = datetime.fromtimestamp(int(id_board[0:8],16))
utc_creation_time = pytz.utc.localize(creation_time)
R Example
1
2
3
cardID = "4d5ea62fd76aa1136000000c"
timestamp = strtoi(strtrim(cardID, 8), 16L)
dateCrceated = as.POSIXct(timestamp, origin = "1970-01-01")
PHP Example
1
2
3
4
5
<?php
$cardID = '4d5ea62fd76aa1136000000c';
$createdDate = date('r', hexdec( substr( $cardID , 0, 8 ) ) );
echo $createdDate;
?>

newObjectId = ObjectId()

ObjectId("507f1f77bcf86cd799439011")
ObjectId("507f191e810c19729de860ea").toString()
507f191e810c19729de860ea
newObjectId = ObjectId(32)
ObjectId("00000020f51bb4362eee2a4d")
newObjectId = ObjectId("507f191e810c19729de860ea")










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

import { storage, startsWith } from '@forge/api';

// Nested entities
await storage.set('survey-responses#1#{UUID}', { });
await storage.set('survey-responses#1#{UUID}', { });
await storage.set('survey-responses#1#{UUID}', { });
await storage.set('survey-responses#1#{UUID}', { });

const results = await storage
  .query()
  .where('key', startsWith('survey-response#1#'))
  .limit(10)
  .getMany();
  
// Fetch 15 results
const { nextCursor } = await storage
    .query()
    .limit(15)
    .where('key', startsWith('account.'))
    .getMany();

// This is expected usage
await storage.query()
    .limit(15)
    .where('key', startsWith('account.'))
    .cursor(nextCursor)
    .getMany();

// This will produce undefined results
await storage.query()
    .cursor(nextCursor)
    .getMany();

    import { storage, startsWith } from '@forge/api';

await storage.query()
  // Filter the response to only keys that start with the string 'value'
  .where('key', startsWith('value'))

  // Limit the result size to 10 values, up to a maximum of 20
  .limit(10)

  // Use the cursor provided (returned from a previous invocation)
  // Cursors shouldn't be persisted
  .cursor('...')

  // Get a list of results
  .getMany();
query.where(field: 'key', condition: Predicate): Query
startsWith(value: string): Predicate
query.cursor(after: string): Query;
query.getMany(): Promise<ListResult>;

interface ListResult {
  results: Result[];
  nextCursor?: string;
}

export interface Result {
  key: string;
  value: object;
}
query.getOne(): Promise<Result | undefined>;

export interface Result {
  key: string;
  value: object;
}

function storageAvailable(type) {
  let storage;
  try {
    storage = window[type];
    const x = "__storage_test__";
    storage.setItem(x, x);
    storage.removeItem(x);
    return true;
  } catch (e) {
    return (
      e instanceof DOMException &&
      // everything except Firefox
      (e.code === 22 ||
        // Firefox
        e.code === 1014 ||
        // test name field too, because code might not be present
        // everything except Firefox
        e.name === "QuotaExceededError" ||
        // Firefox
        e.name === "NS_ERROR_DOM_QUOTA_REACHED") &&
      // acknowledge QuotaExceededError only if there's something already stored
      storage &&
      storage.length !== 0
    );
  }
}

if (storageAvailable("localStorage")) {
  // Yippee! We can use localStorage awesomeness
} else {
  // Too bad, no localStorage for us
}
if (!localStorage.getItem("bgcolor")) {
  populateStorage();
} else {
  setStyles();
}

var WHITE_ICON = 'https://cdn.hyperdev.com/us-east-1%3A3d31b21c-01a0-4da2-8827-4bc6e88b7618%2Ficon-white.svg';
var BLACK_ICON = 'https://cdn.hyperdev.com/us-east-1%3A3d31b21c-01a0-4da2-8827-4bc6e88b7618%2Ficon-black.svg';

var onBtnClick = function (t, opts) {
  console.log('Someone clicked the button');
};

window.TrelloPowerUp.initialize({
  'board-buttons': function (t, opts) {
    return [{
      // we can either provide a button that has a callback function
      icon: {
        dark: WHITE_ICON,
        light: BLACK_ICON
      },
      text: 'Callback',
      callback: onBtnClick,
      condition: 'edit'
    }, {
      // or we can also have a button that is just a simple url
      // clicking it will open a new tab at the provided url
      icon: {
        dark: WHITE_ICON,
        light: BLACK_ICON
      },
      text: 'URL',
      condition: 'always',
      url: 'https://trello.com/inspiration',
      target: 'Inspiring Boards' // optional target for above url
    }];
  }
});
// an example board button object
{
  icon: {
    dark: "https://example.com/a-white-icon.png",
    light: "https://example.com/a-black-icon.png"
  },
  text: "My Board Button",
  callback: function(t) { console.log('clicked'); }
}
window.TrelloPowerUp.initialize({
  "board-buttons": function (t, opts) {
    return t.board("all").then(function (board) {
      console.log(JSON.stringify(board, null, 2));
    });
  },
});
window.TrelloPowerUp.initialize({
  "board-buttons": function (t, opts) {
    return t.board("id", "name").then(function (board) {
      console.log(JSON.stringify(board, null, 2));
    });
  },
});
window.TrelloPowerUp.initialize({
  "card-buttons": function (t, opts) {
    return t.list("all").then(function (list) {
      console.log(JSON.stringify(list, null, 2));
    });
  },
});
window.TrelloPowerUp.initialize({
  "board-buttons": function (t, opts) {
    return t.lists("all").then(function (lists) {
      console.log(JSON.stringify(lists, null, 2));
    });
  },
});
window.TrelloPowerUp.initialize({
  "card-buttons": function (t, opts) {
    return t.card("all").then(function (card) {
      console.log(JSON.stringify(card, null, 2));
    });
  },
});
window.TrelloPowerUp.initialize({
  "board-buttons": function (t, opts) {
    return t.cards("all").then(function (cards) {
      console.log(JSON.stringify(cards, null, 2));
    });
  },
});

var t = window.TrelloPowerUp.iframe();

return t.member("all").then(function (member) {
  console.log(JSON.stringify(member, null, 2));
});
window.TrelloPowerUp.initialize({
  'card-buttons': function (t, opts) {
    console.log(t.memberCanWriteToModel('card'));
    return [];
  }
});
window.TrelloPowerUp.initialize({
  'card-buttons': function (t, opts) {
    console.log(t.isMemberSignedIn());
    return [];
  }
});

var t = window.TrelloPowerUp.iframe();

return t.organization("all").then(function (organization) {
  console.log(JSON.stringify(organization, null, 2));
});
var t = window.TrelloPowerUp.iframe();

return t.organization("id", "name").then(function (organization) {
  console.log(JSON.stringify(organization, null, 2));
});
window.TrelloPowerUp.initialize({
  "card-badges": function (t, opts) {
    let cardAttachments = opts.attachments; // Trello passes you the attachments on the card
    return t
      .card("name")
      .get("name")
      .then(function (cardName) {
        console.log("We just loaded the card name for fun: " + cardName);
        return [
          {
            // Dynamic badges can have their function rerun
            // after a set number of seconds defined by refresh.
            // Minimum of 10 seconds.
            dynamic: function () {
              // we could also return a Promise that resolves to
              // this as well if we needed to do something async first
              return {
                text: "Dynamic " + (Math.random() * 100).toFixed(0).toString(),
                icon: "./images/icon.svg",
                color: "green",
                refresh: 10, // in seconds
              };
            },
          },
          {
            // It's best to use static badges unless you need your
            // badges to refresh.
            // You can mix and match between static and dynamic
            text: "Static",
            icon: HYPERDEV_ICON, // for card front badges only
            color: null,
          },
        ];
      });
  },
});
app:
  id: "ari:cloud:ecosystem::app/406d303d-0393-4ec4-ad7c-1435be94583a"
  licensing:
    enabled: true 

    npm i glob
Note the npm package name is not node-glob that's a different thing that was abandoned years ago. Just glob.

// load using import
import { glob, globSync, globStream, globStreamSync, Glob } from 'glob'
// or using commonjs, that's fine, too
const {
  glob,
  globSync,
  globStream,
  globStreamSync,
  Glob,
} = require('glob')

// the main glob() and globSync() resolve/return array of filenames

// all js files, but don't look in node_modules
const jsfiles = await glob('**/*.js', { ignore: 'node_modules/**' })

// pass in a signal to cancel the glob walk
const stopAfter100ms = await glob('**/*.css', {
  signal: AbortSignal.timeout(100),
})

// multiple patterns supported as well
const images = await glob(['css/*.{png,jpeg}', 'public/*.{png,jpeg}'])

// but of course you can do that with the glob pattern also
// the sync function is the same, just returns a string[] instead
// of Promise<string[]>
const imagesAlt = globSync('{css,public}/*.{png,jpeg}')

// you can also stream them, this is a Minipass stream
const filesStream = globStream(['**/*.dat', 'logs/**/*.log'])

// construct a Glob object if you wanna do it that way, which
// allows for much faster walks if you have to look in the same
// folder multiple times.
const g = new Glob('**/foo', {})
// glob objects are async iterators, can also do globIterate() or
// g.iterate(), same deal
for await (const file of g) {
  console.log('found a foo file:', file)
}
// pass a glob as the glob options to reuse its settings and caches
const g2 = new Glob('**/bar', g)
// sync iteration works as well
for (const file of g2) {
  console.log('found a bar file:', file)
}

// you can also pass withFileTypes: true to get Path objects
// these are like a Dirent, but with some more added powers
// check out http://npm.im/path-scurry for more info on their API
const g3 = new Glob('**/baz/**', { withFileTypes: true })
g3.stream().on('data', path => {
  console.log(
    'got a path object',
    path.fullpath(),
    path.isDirectory(),
    path.readdirSync().map(e => e.name)
  )
})

// if you use stat:true and withFileTypes, you can sort results
// by things like modified time, filter by permission mode, etc.
// All Stats fields will be available in that case. Slightly
// slower, though.
// For example:
const results = await glob('**', { stat: true, withFileTypes: true })

const timeSortedFiles = results
  .sort((a, b) => a.mtimeMs - b.mtimeMs)
  .map(path => path.fullpath())

const groupReadableFiles = results
  .filter(path => path.mode & 0o040)
  .map(path => path.fullpath())

// custom ignores can be done like this, for example by saying
// you'll ignore all markdown files, and all folders named 'docs'
const customIgnoreResults = await glob('**', {
  ignore: {
    ignored: p => /\.md$/.test(p.name),
    childrenIgnored: p => p.isNamed('docs'),
  },
})

// another fun use case, only return files with the same name as
// their parent folder, plus either `.ts` or `.js`
const folderNamedModules = await glob('**/*.{ts,js}', {
  ignore: {
    ignored: p => {
      const pp = p.parent
      return !(p.isNamed(pp.name + '.ts') || p.isNamed(pp.name + '.js'))
    },
  },
})

// find all files edited in the last hour, to do this, we ignore
// all of them that are more than an hour old
const newFiles = await glob('**', {
  // need stat so we have mtime
  stat: true,
  // only want the files, not the dirs
  nodir: true,
  ignore: {
    ignored: p => {
      return new Date() - p.mtime > 60 * 60 * 1000
    },
    // could add similar childrenIgnored here as well, but
    // directory mtime is inconsistent across platforms, so
    // probably better not to, unless you know the system
    // tracks this reliably.
  },
})
$ glob -h

Usage:
  glob [options] [<pattern> [<pattern> ...]]

Expand the positional glob expression arguments into any matching file system
paths found.

  -c<command> --cmd=<command>
                         Run the command provided, passing the glob expression
                         matches as arguments.

  -A --all               By default, the glob cli command will not expand any
                         arguments that are an exact match to a file on disk.

                         This prevents double-expanding, in case the shell
                         expands an argument whose filename is a glob
                         expression.

                         For example, if 'app/*.ts' would match 'app/[id].ts',
                         then on Windows powershell or cmd.exe, 'glob app/*.ts'
                         will expand to 'app/[id].ts', as expected. However, in
                         posix shells such as bash or zsh, the shell will first
                         expand 'app/*.ts' to a list of filenames. Then glob
                         will look for a file matching 'app/[id].ts' (ie,
                         'app/i.ts' or 'app/d.ts'), which is unexpected.

                         Setting '--all' prevents this behavior, causing glob to
                         treat ALL patterns as glob expressions to be expanded,
                         even if they are an exact match to a file on disk.

                         When setting this option, be sure to enquote arguments
                         so that the shell will not expand them prior to passing
                         them to the glob command process.

  -a --absolute          Expand to absolute paths
  -d --dot-relative      Prepend './' on relative matches
  -m --mark              Append a / on any directories matched
  -x --posix             Always resolve to posix style paths, using '/' as the
                         directory separator, even on Windows. Drive letter
                         absolute matches on Windows will be expanded to their
                         full resolved UNC maths, eg instead of 'C:\foo\bar', it
                         will expand to '//?/C:/foo/bar'.

  -f --follow            Follow symlinked directories when expanding '**'
  -R --realpath          Call 'fs.realpath' on all of the results. In the case
                         of an entry that cannot be resolved, the entry is
                         omitted. This incurs a slight performance penalty, of
                         course, because of the added system calls.

  -s --stat              Call 'fs.lstat' on all entries, whether required or not
                         to determine if it's a valid match.

  -b --match-base        Perform a basename-only match if the pattern does not
                         contain any slash characters. That is, '*.js' would be
                         treated as equivalent to '**/*.js', matching js files
                         in all directories.

  --dot                  Allow patterns to match files/directories that start
                         with '.', even if the pattern does not start with '.'

  --nobrace              Do not expand {...} patterns
  --nocase               Perform a case-insensitive match. This defaults to
                         'true' on macOS and Windows platforms, and false on all
                         others.

                         Note: 'nocase' should only be explicitly set when it is
                         known that the filesystem's case sensitivity differs
                         from the platform default. If set 'true' on
                         case-insensitive file systems, then the walk may return
                         more or less results than expected.

  --nodir                Do not match directories, only files.

                         Note: to *only* match directories, append a '/' at the
                         end of the pattern.

  --noext                Do not expand extglob patterns, such as '+(a|b)'
  --noglobstar           Do not expand '**' against multiple path portions. Ie,
                         treat it as a normal '*' instead.

  --windows-path-no-escape
                         Use '\' as a path separator *only*, and *never* as an
                         escape character. If set, all '\' characters are
                         replaced with '/' in the pattern.

  -D<n> --max-depth=<n>  Maximum depth to traverse from the current working
                         directory

  -C<cwd> --cwd=<cwd>    Current working directory to execute/match in
  -r<root> --root=<root> A string path resolved against the 'cwd', which is used
                         as the starting point for absolute patterns that start
                         with '/' (but not drive letters or UNC paths on
                         Windows).

                         Note that this *doesn't* necessarily limit the walk to
                         the 'root' directory, and doesn't affect the cwd
                         starting point for non-absolute patterns. A pattern
                         containing '..' will still be able to traverse out of
                         the root directory, if it is not an actual root
                         directory on the filesystem, and any non-absolute
                         patterns will still be matched in the 'cwd'.

                         To start absolute and non-absolute patterns in the same
                         path, you can use '--root=' to set it to the empty
                         string. However, be aware that on Windows systems, a
                         pattern like 'x:/*' or '//host/share/*' will *always*
                         start in the 'x:/' or '//host/share/' directory,
                         regardless of the --root setting.

  --platform=<platform>  Defaults to the value of 'process.platform' if
                         available, or 'linux' if not. Setting --platform=win32
                         on non-Windows systems may cause strange behavior!

  -i<ignore> --ignore=<ignore>
                         Glob patterns to ignore Can be set multiple times
  -v --debug             Output a huge amount of noisy debug information about
                         patterns as they are parsed and used to match files.

  -h --help              Show this usage information
glob(pattern: string | string[], options?: GlobOptions) => Promise<string[] | Path[]>

Perform an asynchronous glob search for the pattern(s) specified. Returns Path objects if the withFileTypes option is set to true. See below for full options field desciptions.

globSync(pattern: string | string[], options?: GlobOptions) => string[] | Path[]

Synchronous form of glob().

Alias: glob.sync()

globIterate(pattern: string | string[], options?: GlobOptions) => AsyncGenerator<string>

Return an async iterator for walking glob pattern matches.

Alias: glob.iterate()

globIterateSync(pattern: string | string[], options?: GlobOptions) => Generator<string>

Return a sync iterator for walking glob pattern matches.

Alias: glob.iterate.sync(), glob.sync.iterate()

globStream(pattern: string | string[], options?: GlobOptions) => Minipass<string | Path>

Return a stream that emits all the strings or Path objects and then emits end when completed.

Alias: glob.stream()

globStreamSync(pattern: string | string[], options?: GlobOptions) => Minipass<string | Path>

Syncronous form of globStream(). Will read all the matches as fast as you consume them, even all in a single tick if you consume them immediately, but will still respond to backpressure if they're not consumed immediately.

Alias: glob.stream.sync(), glob.sync.stream()

hasMagic(pattern: string | string[], options?: GlobOptions) => boolean


owner: grateful345i@gmail.com
lowerSeverityPaths:
  - path: atlassian-plugins-test-resources/**
    reasoning: "This is a test directory"
  - path: sonar-aggregator/**
    reasoning: "module that aggregates coverage reports"
  
fileAllSnykTicketsNow: true

<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
   <modelVersion>4.0.0</modelVersion>

    <ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7>
        <groupId>com.atlassian.plugins</groupId>
        <artifactId>atlassian-plugins-parent</artifactId>
        <version>8.1.0-m01-SNAPSHOT</version>
    </parent>

   <artifactId>atlassian-plugins-main</ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7>
   <packaging>jar</packaging>

   <name>Atlassian Plugins Main API</name>
   <description>
        Simplified API for interacting with the plugin framework. Also includes a standalone executable jar for
       simple testing.
   </description>

    <ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7>
        <sonar.coverage.jacoco.xmlReportPaths>${project.basedir}/../${jacoco.report.file}</sonar.coverage.jacoco.xmlReportPaths>
    </properties>

    <dependencies>
        <dependency>
            <groupId>com.atlassian.plugins</groupId>
            <artifactId>atlassian-plugins-core</artifactId>
        </dependency>
        <dependency>
            <groupId>com.atlassian.plugins</groupId>
            <artifactId>atlassian-plugins-osgi</artifactId>
        </dependency>
        <dependency>
            <groupId>com.atlassian.plugins</groupId>
            <artifactId>atlassian-plugins-schema</artifactId>
        </dependency>
        <dependency>
            <groupId>com.atlassian.plugins.test</groupId>
            <artifactId>atlassian-plugins-test</artifactId>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>com.atlassian.profiling</groupId>
            <artifactId>atlassian-profiling</artifactId>
            <scope>test</scope>
        </dependency>

        <dependency>
            <groupId>log4j</groupId>
            <artifactId>log4j</artifactId>
            <scope>provided</scope>
            <optional>true</optional>
        </dependency>
        <dependency>
           <groupId>javax.servlet</groupId>
           <artifactId>javax.servlet-api</artifactId>
           <scope>provided</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
          <ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-shade-plugin</artifactId>
            <executions>
              <execution>
                <phase>package</phase>
                <goals>
                  <goal>shade</goal>
                </goals>
                <ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7>
                  <shadedArtifactAttached>true</shadedArtifactAttached>
                  <shadedClassifierName>standalone</shadedClassifierName>
                  <artifactSet>
                    <excludes>
                      <exclude>junit:junit</exclude>
                    </excludes>
                  </ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7>
                  <relocations>
                    <relocation>
                      <pattern>org.apache.commons.io</pattern>
                      <shadedPattern>com.atlassian.org.apache.commons.io</shadedPattern>
                    </relocation>
                  </relocations>
                </configuration>
              </execution>
            </executions>
          </plugin>
          <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-jar-plugin</artifactId>
            <configuration>
              <archive>
                <ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7>
                  <addClasspath>true</addClasspath>
                  <mainClass>com.atlassian.plugin.main.Main</mainClass>
                </manifest>
              </archive>
            </configuration>
          </plugin>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7>maven-dependency-plugin</artifactId>
                <executions>
                    <execution>
                        <id>extract-framework-bundles</id>
                        <phase>process-resources</phase>
                        <goals>
                            <goal>unpack</goal>
                        </goals>
                        <configuration>
                            <artifactItems>
                                <artifactItem>
                                    <groupId>com.atlassian.platform.dependencies</groupId>
                                    <artifactId>platform-framework-bundles</artifactId>
                                    <version>${new-platform.version}</version>
                                    <type>zip</type>
                                    <outputDirectory>${project.build.directory}/framework-bundles</outputDirectory>
                                </artifactItem>
                            </artifactItems>
                        </configuration>
                    </execution>
                    <execution>
                        <id>copy-test-bundles</id>
                        <phase>process-resources</phase>
                        <goals>
                            <goal>copy</goal>
                        </goals>
                        <configuration>
                            <artifactItems>
                                <artifactItem>
                                    <groupId>org.slf4j</groupId>
                                    <artifactId>jcl-over-slf4j</artifactId>
                                </artifactItem>
                            </artifactItems>
                            <outputDirectory>${project.build.directory}/framework-bundles</outputDirectory>
                        </configuration>
                    </execution>
                </executions>
            </plugin>
            <plugin>
                <artifactId>maven-failsafe-plugin</artifactId>
            </plugin>
        </plugins>
    </build>
</project>

<webwork:component name="'atl_token'" value="/xsrfToken" template="hidden.jsp"/>

<input type="hidden" name="atl_token" value="$atl_token" />

MyAction.jspa?myParameter=true&atl_token=<webwork:property value="/xsrfToken"/>

MyAction.jspa?myParameter=true&atl_token=${ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7}

import com.atlassian.jira.security.xsrf.XsrfTokenGenerator;
XsrfTokenGenerator xsrfTokenGenerator = ComponentManager.getComponentInstanceOfType(XsrfTokenGenerator.class);
String token = xsrfTokenGenerator.generateToken(request);
X-Atlassian-Token: ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7

<init-param>
   <param-name>RequireSecurityToken</param-name>
   <param-value>true</param-value>
</init-param>

1
curl -v https://mysite.atlassian.net --user me@example.com:ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7

1
npm install -g @forge/cli
Verify that the CLI is installed correctly by running:
Copy
1
forge --version
You
forge login
You'll be asked whether to allow Forge to collect usage analytics data:
Copy
1
Allow Forge to collect CLI usage and error reporting information?
Answering Yes will allow Forge to collect data about your app's deployments and installations (including error data). This, in turn, helps us monitor Forge's overall performance and reliability. The collected data also helps us make better decisions on improving Forge's feature set and performance.
For information about how Atlassian collects and handles your data, read our Privacy Policy.
Enter the email address associated with your Atlassian account.
Enter your Atlassian API token. You copied this to the clipboard in step 5.
You will see a message similar to this confirming you are logged in:
Copy
1
✔ Logged in as Mia Krystof
The Forge CLI uses your operating system's keychain to securely store your login details. Any command after forge login that requires authentication will read your credentials from the keychain. When this occurs, your keychain may prompt you for access; approve it to allow the CLI to run the command.
On Linux, you'll need libsecret installed to perform this step.
Using environment variables to login
If a keychain isn't available, you can store your login email and token through the environment variables FORGE_EMAIL and FORGE_API_TOKEN, respectively. In continuous integration environments, you can store these environment variables as secrets for your builds. For more information, read our tutorial on setting up continuous delivery for Forge apps.
Otherwise, you can also set environment variables manually:
Copy
1
2
3
4
5
read FORGE_EMAIL
# Enter email
read -s FORGE_API_TOKEN
# Enter API token (will not be displayed)
export FORGE_EMAIL FORGE_API_TOKEN : ATATT3xFfGF0TstrJdZSp7eSVzf5nN0ZjylWemk_uWlqMBWBszgMh4U0F7rXJyvV2kBFFmu2OkkjFbNXH7PQwATDVXmXTfmx9xn1Ft3AqZVsI4ExTl6whWrBs-2-EzYrcw550kSiXn8EuIhnG4FqxFQUl5dHlHQslxOOdyJowAuBXwkXKUOq4E8=478D1AB7





  
