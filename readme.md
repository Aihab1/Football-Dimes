
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
  <strong>MongoDB | Expressjs | React/Redux | Nodejs</strong>
</p>
    
![Screenshot3](https://user-images.githubusercontent.com/55903466/134020098-b12931d3-c9c8-48fa-a466-fe7824b0e61c.png)

## 🗂 Project Breakdown
    
### 1. API Server (Backend)
    
Directory `server`
    
**Football Dimes Backend supports the following API endpoints:**

`GET` **/players**
  - Read the complete players list

`GET` **/players/:id**
  - Read a player by id

`GET` **/players/search**
  - Read a player by a particular tag / search query

`POST` **/players**
  - Create a player card (authentication required)

`POST` **/players/:id/commentPlayer**
  - Comment on a player profile (authentication required)

`PATCH` **/players**
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
> Supports create, read, update, and delete operations for player cards.

2. **Player profiles**
> Profile features include fetching player-specific news, getting player suggestions, commenting and more.

3. **Search feature**
> Search a player by name / tags.

4. **Liking**
> Like / unlike a player card. (Authentication required for liking)

5. **Pagination**
> Pagination feature for fast and smooth user experience.

6. **Others**
> Player cards support time stamps, edit & delete options, image (base64) & tags, and liking feature. News articles are clickable and direct you to the news source.

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
