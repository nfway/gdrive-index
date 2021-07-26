# GoIndex-theme-acrou 

Without hm.baidu.com , of course.

## Note

1. After I fork this repo, I found some baidu.com code, and I remove them, for good reason.
2. You can change `[index.js](blob/master/go2index)` line 71, from ` version: "1.1"` to ` version: "1.2"`

## How to

1. Open any of the following links

   - [ ] https://install.achirou.workers.dev
   - [ ] https://goindex-quick-install.glitch.me
   - [x] https://goindex-install.herokuapp.com

2. Auth and get the code  

3. Deploy the code to [Cloudflare Workers](https://www.cloudflare.com/)

## Deployment  

1. Open [Google Drive API](https://console.developers.google.com/apis/api/drive.googleapis.com/overview)
2. Create a [OAuth client ID](https://console.developers.google.com/apis/credentials/oauthclient)
3. Install [rclone](https://rclone.org/downloads/) software locally
4. Get `refresh_token ` with `rclone`
5. Download `index.js` in https://github.com/nfway/gdrive-index/blob/master/go2index/ ,replace `client_id`,`client_secret`,`refresh_token` , change line 71 `version: "1.1"` into  `version: "1.2"`.
6. Deploy the code to [Cloudflare Workers](https://www.cloudflare.com/)

> If you write a good article and want to share it with others, please submit Issues and I will post the link here.

## Options

### Video

| Option       | Type                       | Default                                                      | Description                                                  |
| ------------ | -------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `api`        | String                     | `''`                                                         | External video player api. When this value is not null, all of the following options do not work |
| `autoplay`   | Boolean                    | `true`                                                       | When set to true, the video plays automatically, depending on whether the browser supports the |
| `invertTime` | Boolean                    | `false`                                                      | Display the current time as a countdown rather than an incremental counter. |
| `controls`   | Array, Function or Element | `['play-large', 'restart', 'play', 'progress', 'current-time', 'duration', 'mute', 'volume', 'captions', 'settings', 'pip', 'airplay', 'download', 'fullscreen']` | Which buttons are displayed in the control bar. See more [CONTROLS.md](https://github.com/sampotts/plyr/blob/master/CONTROLS.md#using-default-controls) |
| `settings`   | Array                      | `['quality', 'speed', 'loop']`                               | You can specify which settings to show in the menu           |

For more option, see plyr [options](https://github.com/sampotts/plyr#options)

### Audio

| Option      | Type    | Default    | Description                                                  |
| ----------- | ------- | ---------- | ------------------------------------------------------------ |
| `container` | String  | `.aplayer` | No support for changes                                       |
| `fixed`     | Boolean | `true`     | No support for changes                                       |
| `autoplay`  | Boolean | `false`    | audio autoplay                                               |
| `loop`      | String  | `'all'`    | player loop play, values: 'all', 'one', 'none'               |
| `order`     | String  | `'list'`   | player play order, values: 'list', 'random'                  |
| `preload`   | String  | `'auto'`   | values: 'none', 'metadata', 'auto'                           |
| `volume`    | Number  | `0.7`      | default volume, notice that player will remember user setting, default volume will not work after user set volume themselves |
| `audios`    | Array   | `[]`       | Playlists can be preset. [FAQ](#FAQ)                         |

For more option, see APlayer [options](https://aplayer.js.org/#/home?id=options)

## FAQ

> How do I change the way the list is sorted?

Modify line 636 of the code or search for `params.orderBy`

```javascript
－ params.orderBy = "folder,name,modifiedTime desc";
＋ params.orderBy = "modifiedTime desc";
```

> How to preset an audio playlist?

Audio option add `audios`

```
audio: {
  audios: [
    {
      name: "Mojito",
      artist: "周杰伦",
      url: "https://xx.mp3",
      lrc: "https://xx.lrc",
      cover: "https://xx.jpg"
    }
  ]
}
```


## Lisense

[MIT](LICENSE)

