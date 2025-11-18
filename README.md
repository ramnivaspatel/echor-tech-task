# Echor Tech Task - TypeScript Express API

This project implements a single endpoint `POST /api/transform` which takes a JSON body `{ "sentence": "..." }` and returns:

- `word_count` — number of words (split on whitespace)
- `unique_words` — list of unique words in lowercase in their first-seen order
- `reversed_sentence` — sentence with word order reversed

## Quick start

1. Install dependencies

```bash
npm install
```

2. Run in development (auto restart)

```bash
npm run dev
```

3. Build and run

```bash
npm run build
npm start
```

4. Test with curl

```bash
curl -s -X POST http://localhost:3000/api/transform -H "Content-Type: application/json" -d '{"sentence":"I love working with JavaScript and Node.js"}' | jq
```

Expected response:

```json
{
  "word_count": 7,
  "unique_words": ["i","love","working","with","javascript","and","node.js"],
  "reversed_sentence": "Node.js and JavaScript with working love I"
}
```

## Notes
- Tokenization is whitespace-based intentionally so `Node.js` stays as `node.js` (preserving dots)
- Unique words are lowercased and preserved in first-seen order
