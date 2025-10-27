# 🎬 @vreden/youtube_scraper v1.2.8

Welcome to **@vreden/youtube_scraper** — your all-in-one YouTube scraping, metadata, and download toolkit for Node.js! 🚀

Easily fetch YouTube video and channel metadata, search YouTube, and **download videos or audio in multiple formats** — all with a few lines of code. Whether you're building a bot, a content aggregator, or a research tool, this package makes YouTube integration a breeze.

---

## ✨ Features

- 🔎 **Search** YouTube videos and channels
- 🎵 **Download Audio (MP3)** at 92, 128, 256, or 320 kbps
- 🎥 **Download Video (MP4)** at 144p, 360p, 480p, 720p, or 1080p
- 📝 **Fetch Metadata** for videos and channels
- 🤝 **Multiple Providers** for reliable download options
- 🛡️ No API key required for basic operations!

---

## 🚀 Installation

```bash
npm install @vreden/youtube_scraper
```

---

## ⚡ Quick Start

```js
const yt = require('@vreden/youtube_scraper');

// Download audio as MP3
yt.ytmp3('https://www.youtube.com/watch?v=dQw4w9WgXcQ', 128)
  .then(result => console.log(result));

// Download video as MP4
yt.ytmp4('https://www.youtube.com/watch?v=dQw4w9WgXcQ', 360)
  .then(result => console.log(result));

// Search YouTube
yt.search('lofi hip hop')
  .then(results => console.log(results));

// Get video metadata
yt.metadata('https://www.youtube.com/watch?v=dQw4w9WgXcQ')
  .then(info => console.log(info));

// Get channel metadata
yt.channel('@lofi_girl')
  .then(info => console.log(info));
```

---

## 📚 API Reference

### `.ytmp3(link, quality = 128)`

Download YouTube audio as MP3.  
- `link` — YouTube URL or video ID  
- `quality` — Audio quality (`92`, `128`, `256`, `320` kbps)

### `.ytmp4(link, quality = 360)`

Download YouTube video as MP4.  
- `link` — YouTube URL or video ID  
- `quality` — Video quality (`144`, `360`, `480`, `720`, `1080` p)

### `.apimp3(link, quality = 128)`

Alternative MP3 downloader (uses api.vreden.my.id).  
- Same params as `.ytmp3`.

### `.apimp4(link, quality = 360)`

Alternative MP4 downloader (uses api.vreden.my.id).  
- Same params as `.ytmp4`.

### `.search(query)`

Search YouTube for videos/channels/playlists.  
- `query` — Any search string

### `.metadata(link)`

Fetch detailed video metadata.  
- `link` — YouTube video URL or ID

### `.channel(usernameOrUrl)`

Fetch channel metadata.  
- `usernameOrUrl` — YouTube channel URL or username (`@handle` or custom URL)

---

## 🟢 Example Output

### Downloader Result Example

```json
{
  "status": true,
  "creator": "@vreden/youtube_scraper",
  "metadata": {
    "type": "video",
    "videoId": "QqJ9zrY_ITw",
    "url": "https://youtube.com/watch?v=QqJ9zrY_ITw",
    "title": "Issam Alnajjar - Hadal Ahbek (Performance Video)",
    "description": "اغنية \" حضل أحبك \". Singer/Songwriter : Issam Alnajjar Issam's instagram : https://instagram.com/issamalnajjar?igshid= ...",
    "image": "https://i.ytimg.com/vi/QqJ9zrY_ITw/hq720.jpg",
    "thumbnail": "https://i.ytimg.com/vi/QqJ9zrY_ITw/hq720.jpg",
    "seconds": 211,
    "timestamp": "3:31",
    "duration": { "seconds": 211, "timestamp": "3:31" },
    "ago": "5 years ago",
    "views": 182118356,
    "author": {
      "name": "Issam Alnajjar",
      "url": "https://youtube.com/channel/UCrjyDI5SQnxBbGnUpnfT2NA"
    }
  },
  "download": {
    "status": true,
    "quality": "128kbps",
    "availableQuality": [92, 128, 256, 320],
    "url": "https://cdn406.savetube.vip/media/QqJ9zrY_ITw/issam-alnajjar-hadal-ahbek-performance-video-128-ytshorts.savetube.me.mp3",
    "filename": "Issam Alnajjar - Hadal Ahbek (Performance Video) (128kbps).mp3"
  }
}
```

---

### Metadata Result Example

```json
{
  "id": "QqJ9zrY_ITw",
  "channel_id": "UCrjyDI5SQnxBbGnUpnfT2NA",
  "channel_title": "Issam Alnajjar",
  "title": "Issam Alnajjar - Hadal Ahbek (Performance Video)",
  "description": "اغنية \" حضل أحبك \" \n______________\n\nSinger...",
  "thumbnails": [
    {
      "quality": "default",
      "url": "https://i.ytimg.com/vi/QqJ9zrY_ITw/default.jpg",
      "width": 120,
      "height": 90
    },
    {
      "quality": "medium",
      "url": "https://i.ytimg.com/vi/QqJ9zrY_ITw/mqdefault.jpg",
      "width": 320,
      "height": 180
    },
    {
      "quality": "high",
      "url": "https://i.ytimg.com/vi/QqJ9zrY_ITw/hqdefault.jpg",
      "width": 480,
      "height": 360
    },
    {
      "quality": "standard",
      "url": "https://i.ytimg.com/vi/QqJ9zrY_ITw/sddefault.jpg",
      "width": 640,
      "height": 480
    },
    {
      "quality": "maxres",
      "url": "https://i.ytimg.com/vi/QqJ9zrY_ITw/maxresdefault.jpg",
      "width": 1280,
      "height": 720
    }
  ],
  "tags": [
    "الأردن",
    "حب",
    "موسيقى بديلة",
    "فيديو كليب",
    "فلسطين",
    "عصام النجار",
    "Jordan",
    "love",
    "music video"
  ],
  "published_date": "2020-09-27T17:00:09Z",
  "published_format": "28 Sep 2020, 00:00 WIB",
  "statistics": {
    "like": "3939033",
    "view": "182118356",
    "favorit": "0",
    "comment": "287527"
  }
}
```

---

### Channel Metadata Example

```json
{
  "id": "UCX6OQ3DkcsbYNE6H8uQQuVA",
  "title": "MrBeast",
  "description": "SUBSCRIBE FOR A COOKIE!\nNew MrBeast or...",
  "username": "@mrbeast",
  "thumbnails": [
    {
      "quality": "default",
      "url": "https://yt3.ggpht.com/nxYrc_1_2f77DoBadyxMTmv7ZpRZapHR5jbuYe7PlPd5cIRJxtNNEYyOC0ZsxaDyJJzXrnJiuDE=s88-c-k-c0x00ffffff-no-rj",
      "width": 88,
      "height": 88
    },
    {
      "quality": "medium",
      "url": "https://yt3.ggpht.com/nxYrc_1_2f77DoBadyxMTmv7ZpRZapHR5jbuYe7PlPd5cIRJxtNNEYyOC0ZsxaDyJJzXrnJiuDE=s240-c-k-c0x00ffffff-no-rj",
      "width": 240,
      "height": 240
    },
    {
      "quality": "high",
      "url": "https://yt3.ggpht.com/nxYrc_1_2f77DoBadyxMTmv7ZpRZapHR5jbuYe7PlPd5cIRJxtNNEYyOC0ZsxaDyJJzXrnJiuDE=s800-c-k-c0x00ffffff-no-rj",
      "width": 800,
      "height": 800
    }
  ],
  "banner": "https://yt3.googleusercontent.com/5KWiriZZ_KEoEdSMFTJKj2M6vR_XSiRZeQ-ix0cvG3TGZuGoi8sfAjrSiZAP0GzXBkmF8ZGytw",
  "published_date": "2012-02-20T00:43:50Z",
  "published_format": "20 Feb 2012, 07:43 WIB",
  "statistics": {
    "view": "98788932632",
    "video": "913",
    "subscriber": "448000000"
  }
}
```

---

## 💌 Contact & Community

- **WhatsApp Developer:** [wa.me/6285643115199](https://wa.me/6285643115199)
- **WhatsApp Channel:** [whatsapp.com/channel/0029Vaf0HPMLdQeZsp3XRp2T](https://whatsapp.com/channel/0029Vaf0HPMLdQeZsp3XRp2T)

Feel free to reach out for feature requests, bug reports, or just to say hi! We love hearing from developers. ✨

---

## 🛠️ Requirements

- Node.js v14+ recommended
- Internet connection

---

## ⚠️ Disclaimer

This module is intended for **educational and personal use only**. Downloading copyrighted material without permission may violate YouTube’s Terms of Service.

---

## ⭐️ Star & Share!

If you find this project useful, please star ⭐️ the repo and share it with your friends!

---

Made with ❤️ by [@vreden](https://www.rumahotp.com)