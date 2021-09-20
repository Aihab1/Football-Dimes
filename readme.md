
<h1 align="center">
  <a href="https://football-dimes.herokuapp.com">
    Football Dimes
  </a>
</h1>

<p align="center">
  Football Dimes is a football-themed social media web application built upon the MERN stack.
  <br>
  It allows users to post about their favourite football players, like posts made by other users, get player-specific news, and create sections for discussing players, leagues, and clubs.
</p>
<p align="center">
  <strong><img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white" /> <img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" /> <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" /> <img src="https://img.shields.io/badge/Redux-593D88?style=for-the-badge&logo=redux&logoColor=white" /> <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" /></strong>
</p>
    
![Screenshot3](https://user-images.githubusercontent.com/55903466/134020098-b12931d3-c9c8-48fa-a466-fe7824b0e61c.png)

## 🗂 Project Breakdown
    
### 1. API Server (Backend)
    
Directory `server`
    
**Football Dimes Backend supports the following API endpoints:**

`GET` **/players**
  - Read the complete players list

> Successful (200 status code) response is of the form:

```
{
    "data": [
        {
            "_id": "some_player_id",
            "player_name": "Lionel Messi",
            "description": "some_description"
            "name": "creator_name",
            "creator": "creator_id",
            "tags": ["goat", "psg", "argentina", ...],
            "selectedFile": "data:image/jpeg;base64... (base64 image)",
            "likes": ["user_id1", "user_id2", ... , "user_id(n)"],
            "comments": ["commaent1", "comment2", ... , "comment(n)"],
            "createdAt": "2021-XX-16T14:37:41.840Z"
        }, {
            "_id": "some_player_id_2",
             ...
        },
        ...
    ],
    "currentPage": 1,
    "numberOfPages": 30
}
```

`GET` **/players/:id**
  - Read a player by id

> Successful (200 status code) response is of the form:

```
{
    "data": {
        "_id": "some_player_id",
        "player_name": "Memphis Depay",
        "description": "some_description",
        "name": "creator_name",
        "creator": "creator_id",
        "tags": ["tag1", "tag2", "tag3", ...],
        "selectedFile": "data:image/jpeg;base64 (image file)",
        "likes": ["user_id1", "user_id2", ...],
        "comments": ["comment1", "comment2", ...],
        "createdAt": "2021-XX-16T14:52:52.812Z",
        "articles": [array_of_news_articles (see newsapi.org documentation)]
     }
}
```

`GET` **/players/search**
  - Read a player by a particular tag / search query

> Same response as GET /players/:id, search terms are sent as query params.

`POST` **/players**
  - Create a player card (authentication required)

`POST` **/players/:id/commentPlayer**
  - Comment on a player profile (authentication required)

`PATCH` **/players/:id**
  - Update a player card (authentication required, only the creator can update)

`PATCH` **/players/:id/likePlayer**
  - Like a player (authentication required)

`DELETE` **/players/:id**
  - Delete a player card (authentication required, only the creator can delete)

#### Authentication Endpoints:

`POST` **/users/signup**
  - Create an account
> Requires an object with firstName, lastName, email, password, and confirmPassword attributes. Any field should not be null.

`POST` **/users/signin**
  - Sign in 
> Requires an object with email and password attributes. Any field should not be null.

### 2. React Client (Frontend)

Directory `client`

#### Features:

1. **Complete CRUD functionality**
    - Supports create, read, update, and delete operations for player cards.

2. **Player profiles**
    - Profile features include fetching player-specific news, getting player suggestions, commenting, and more.

3. **Search feature**
    - Search a player by name / tags.

4. **Liking**
    - Like / unlike a player card. (Authentication required for liking)

5. **Pagination**
    - Pagination feature for fast and smooth user experience.

6. **Others**
    - Player cards support time stamps, edit & delete options, image (base64) & tags, and liking feature. News articles are clickable and direct you to the news source.

### 3. MongoDB + Mongoose Models (Database)

The website uses MongoDB cloud database for storing the data fields efficiently. Mongoose is used for creating playerCard schema and user schema (for authentication).

## 🖼 Website Images

![Screenshot1](https://user-images.githubusercontent.com/55903466/134033200-0c339bc2-1ebb-4ac0-bec5-91f395eccc26.png)
![Screenshot2](https://user-images.githubusercontent.com/55903466/134033213-a48de406-9b22-466f-afe2-7e610a693153.png)

## ▶ Run the project locally

### 1. Clone the `Football-Dimes` repository
```
git clone https://github.com/Aihab1/Football-Dimes.git
# cd into server and client one by one and refer .env.example file to create your own .env file for storing environment variables. Please make sure you complete this step before running the application.
```

### 2. Install package dependencies

Open two terminals to run commands parallely.

**First terminal (client):**
```
cd client
npm install
```

**Second terminal (server):**
```
cd server
npm install
```

### 3. Start development servers

Continue where you left off (two terminals opened).

**First terminal (client):**
```
npm start
```

**Second terminal (server):**
```
npm start
```

> Backend server runs on localhost:5000 and the client-side runs on localhost:3000 by default.
