# Add a news item

Edit **news.js** to update **News**.
This works both on the live website and when opening `index.html` locally.

1. Open `news.js` in a text editor, or use the pencil button to edit it on GitHub.
2. Copy an entry inside the `window.VITAMIN_NEWS = [ ... ];` list.
3. Change the values and save. On GitHub, commit the change: the news item will appear after the website's usual update.

## Copyable entry

```js
  {
    date: "2026-11-18",
    category: "News",
    title: "New announcement title",
    url: "https://example.com/"
  },
```

Paste it **immediately after `[`**, before the first existing entry.
The trailing comma separates the new entry from the next one. Keep text and dates in quotes.
The website sorts news items automatically, newest first.

Use `\n` inside `title` to start a new line, for example `title: "New announcement.\nApply by 3 December 2026."`.

| Field | Usage |
| --- | --- |
| `date` | Required. Use `"2026-11-18"`, or `"2026-11"` to show only the month and year. |
| `title` | Required. The news title, as plain text. |
| `category` | Optional. For example, `"Publication"`, `"Event"`, `"Release"` or `"Job opening"`. |
| `url` | Optional. An `https://...` link or a section link such as `"#publications"`. Omit it to keep the title as plain text. |
| `linkText` | Optional. The exact part of the title to make clickable. If omitted, the link applies to the whole title. |
| `links` | Optional. Multiple links in one title: each item has `text` (the exact words in the title) and `url`. When present, this replaces the entry's `url` and `linkText`. |
| `draft` | Optional. Add `draft: true` to hide an entry while preparing it; remove the field when it is ready to appear. |

To remove a news item, delete its entry. To hide it temporarily, use `draft: true`.
For a title containing double quotes, write `\"`, for example `title: "New \"VITAMIN pills\" episode"`.

The two original news items were moved into `news.js`. Future updates only require editing this file.

## Multiple links in a brief announcement

Keep one short title and make the words identifying each announcement or resource clickable:

```js
  {
    date: "2026-11-19",
    category: "News",
    title: "New resources: Documentation and GitHub.",
    links: [
      { text: "Documentation", url: "https://vitamin.r2.enst.fr/documentation/" },
      { text: "GitHub", url: "https://github.com/VITAMIN-organisation/vitamin-model-checker" }
    ]
  },
```

Each link's text must exactly match the corresponding words in the title. Entries with a single `url` continue to work as before.

## Archive by year

The **News** button keeps the same name every year. Entries are grouped automatically by year, newest first, using the `date` field.
An entry dated `"2027-01-10"` creates a **2027** group above **2026**, preserving previous news without changing the HTML.
To correct the publication date, edit `date`; a deadline mentioned in the title remains separate information.
