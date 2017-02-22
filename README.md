# metalsmith-metadata-in-filename
A Metalsmith plugin to extract the date, slug, and title from your filenames

## Features

- pulls `date` from filename, using configurable format (`YYYY-MM-DD` by default)
- pulls `slug` (ideal for use in URLs) from filename
- creates `title` from filename, this is the slug minus punctuation, plus Title Case
- adds these properties to the file metadata

## Installation

```bash
$ npm install --save-dev metalsmith-metadata-in-filename
```

## Usage

### Use metadata in your filenames

```bash
2017-03-03-this-is-a-slug.md
20170101-custom-date-format.md
```

### Configure your build

```javascript
import metadataInFilename from 'metalsmith-metadata-in-filename'

metalsmith.use(metadataInFilename())
```

Optionally set `force: true` to overwrite existing metadata

```javascript
metalsmith.use(metadataInFilename({
  force: true
}))
```

You can also use a custom date format

```javascript
metalsmith.use(metadataInFilename({
  format: 'YYYYMMDD'
}))
```

## CLI Usage

```json
{
  "plugins": {
    "metalsmith-metadata-in-filename": {
      "force": false,
      "format": "YYYY-MM-DD"
    }
  }
}
```

## License

MIT License

Copyright (c) 2017 Yann Eves &lt;hello@yanneves.com&gt;

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
