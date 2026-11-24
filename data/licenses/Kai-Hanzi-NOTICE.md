# Sources and licensing

## Why there are no stroke paths in this dataset

The obvious thing to ship alongside HSK characters is stroke path and median data. We deliberately do not, and the reason is licensing rather than effort.

The standard open source of that data is [`hanzi-writer-data`](https://github.com/chanind/hanzi-writer-data), which derives from [Make Me A Hanzi](https://github.com/skishore/makemeahanzi), which in turn extracts outlines from fonts released by Arphic Technology under the **[Arphic Public License](https://github.com/chanind/hanzi-writer-data/blob/master/ARPHICPL.TXT)**. Part of the data (from AnimCJK) is **LGPL v3 or later**.

Both are copyleft. Redistributing derived stroke data would require this dataset to carry those terms — modified files must be marked, and the whole must stay freely available under the same license. That is a perfectly reasonable license to comply with, but folding it into a dataset whose value is being *vendored and remixed* would force every downstream user to reason about a font copyleft they did not ask for.

So the split is clean:

- **This dataset** — only material Kai Hanzi authored (Sino-Vietnamese readings, radical glosses, mnemonics, stroke hints) plus uncopyrightable facts (pinyin, stroke counts, HSK bands). CC BY 4.0, no strings.
- **Stroke geometry** — fetch from `hanzi-writer-data` yourself, under its own terms.

Joining is one line, since both are keyed by the character itself:

```js
const chars = await fetch("https://raw.githubusercontent.com/…/data/characters.json").then((r) => r.json());

async function withStrokes(entry) {
  const url = `https://cdn.jsdelivr.net/npm/hanzi-writer-data@2/${entry.hanzi}.json`;
  const { strokes, medians } = await fetch(url).then((r) => r.json());
  return { ...entry, strokes, medians };
}
```

If you redistribute the result, the combined work carries the Arphic Public License / LGPL obligations for the stroke portion. Read those licenses rather than taking this file's word for it.

## Provenance of each field

| Field | Origin | Status |
|---|---|---|
| `sinoViet`, `mnemonic`, `strokeHint`, radical glosses | Written by Kai Hanzi | Original work, CC BY 4.0 |
| `meaningVi` | Written by Kai Hanzi | Original work, CC BY 4.0 |
| `pinyin`, `strokeCount`, `traditional` | Standard reference facts | Facts, not copyrightable |
| `hskLevel` | The band Kai Hanzi teaches the character in, following the HSK 3.0 syllabus | A factual mapping; the underlying syllabus is published by Chinese Ministry of Education bodies and is not reproduced here |

The dataset contains no vocabulary lists, no example sentences, no textbook text, and no material copied from another HSK dataset.

## Corrections

If you believe something here infringes a license, open an issue and it will be removed while we look into it. That is a faster path than the alternatives and we would rather know.
