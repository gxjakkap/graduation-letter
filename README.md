# graduation-letter
Website I built as a graduation letter for some of my friends and junior.

## Prerequisite

* Node 16
* Yarn 3 recommended

## Build Setup

```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

## Included features

- Paragraph
- Image
- Spotify Song Iframe

## How-to

* Edit data in static/data.json like so

```json
    {
        "slug": "page1-QIPYt", //slug
        "usrname": "example1", //username to display, such as instagram handle
        "name": "Mr. Example 1", //nickname
        "paragraph": "This is paragraph 1", //paragraph
        "pr2": "This is paragraph 2 (optional)",
        "pr3": "This is paragraph 3 (optional)",
        "imagelink": "/image.jpg", //image link. image should be in static folder
        "songid": "4cOdK2wGLETKBW3PvgPWqT" // spotify song id. example: 4cOdK2wGLETKBW3PvgPWqT comes from https://open.spotify.com/track/4cOdK2wGLETKBW3PvgPWqT
    },
```

* Run `yarn dev` or `npm run dev` and your result would be at http://localhost:3000/l/{slug}

* Add as much page as you want and then you can deploy to vercel or whatever.

## License
[MIT License](https://github.com/gxjakkap/graduation-letter/blob/main/LICENSE.md)