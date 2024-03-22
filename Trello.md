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











  
