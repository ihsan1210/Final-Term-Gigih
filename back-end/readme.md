## Mid Term GIGIH 3.0 (BACKEND)

## Table Of Content

- [Database Structure](#database-structure)
  - [Videos Collection](#videos-collection)
  - [Comment Collection](#comment-collection)
- [API Structure](#api-structure)
- [lIST API Request Response](#api-request-response)
- [How To Run](#how-to-run-in-local)

## Database Structure

Database name is tokplay and have 2 collections, videos and comments.

### Videos Collection

```
  {
    videoId: string
    urlThumbnail: string
    urlVideo: string
    product : [
      {
        productThumbnail : string
        productId: string
        price: number
        productName: string
        linkProduct: string
      }
    ]
  }
```

### Comments Collection

```
{
  videoId :  string
  username :  string
  comment :  string
}
```

## API Structure
Backend deploy in railway, that can acces in this link: (https://final-term-backend.up.railway.app/)
Endpoint ready to use

```
GET   /video
GET   /video/listProduk/:id
GET   /video/:id
GET   /comment/list/:id
POST  /comment/post
```

## API Request Response

### GET /video

---

Return all videos JSON from database

```
{
  result : [
    {
      videoId,
      urlThumbnail,
      urlVideo: string
      product : [
        {
          productThumbnail : string
          productId,
          productName,
          linkProduct,
          price
        }
      ]
    }
  ]
}
```

### GET /video/listProduk/:id

---

Return List Product in Video Database from the specified video Id

```
{
  result : [
    [
      {
      productId,
      productThumbnail
      productName,
      linkProduct,
      price
      }
    ]
  ]
}
```

### GET /video/:id

---

Find videos from the specified id.

```
{
  result : [
    {
      videoId,
      urlThumbnail,
      product : [
        {
          productId,
          productThumbnail
     	    productName,
          price,
          linkProduct
        }
      ]
    }
  ]
}
```

### GET /comment/list/:id

---

Get all comment from databases with specified video id.

```
{
  result : [
    {
      videoId,
      username,
      comment
    }
  ]
}
```

### POST /comment/post/:id

---

POST / Creates a new Comment and insert to databases with specified video Id.

```
{
  videoId :  string
  username :  string
  comment :  string
}
```

## How To Run In Local

### Installation

This project use express Js version 4.18.2

```
#Make sure to install the dependencies:

"dependencies": {
"body-parser": "^1.20.2",
"dotenv": "^16.3.1",
"express": "^4.18.2",
"mongoose": "^7.4.1",
"nodemon": "^3.0.1"
}
```

# install dependencies

```
npm install express body-parser dotenv mongoose nodemon
```

### Start Server

```
# Run Server
npm start index.js
```

Running on http://localhost:3000
