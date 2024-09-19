# youtube_scraper

A simple YouTube video downloader for audio and video formats.

## Installation

You can install the package using npm:

```bash
npm install youtube_scraper
```

## Usage

```Javascript
const { search, ytmp3, ytmp4 } = require('youtube_scraper');
```

## Download Audio (MP3) 🎧

```Javascript
const url = 'https://www.youtube.com/watch?v=YOUR_VIDEO_ID';

ytmp3(url)
    .then(result => {
        if (result.status) {
            console.log('Download Link:', result.download);
            console.log('Metadata:', result.metadata);
        } else {
            console.error('Error:', result.result);
        }
    });
```

## Download Video (MP4) 🗃️

```Javascript
const url = 'https://www.youtube.com/watch?v=YOUR_VIDEO_ID';

ytmp4(url)
    .then(result => {
        if (result.status) {
            console.log('Download Link:', result.download);
            console.log('Metadata:', result.metadata);
        } else {
            console.error('Error:', result.result);
        }
    });
```

## Search Video 🍟

```Javascript
const query = 'your search term';

search(query)
    .then(result => {
        if (result.status) {
            console.log('Search Results:', result.results);
        } else {
            console.error('Error:', result.result);
        }
    });
```