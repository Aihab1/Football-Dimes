
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

View the complete API documentation <a href="https://github.com/Aihab1/Football-Dimes/tree/main/server#readme">here</a>.

`GET` **/players**

`GET` **/players/:id**

`GET` **/players/search**

`POST` **/players**

`POST` **/players/:id/commentPlayer**

`PATCH` **/players/:id**

`PATCH` **/players/:id/likePlayer**

`DELETE` **/players/:id**
 
#### Authentication Endpoints:

`POST` **/user/signup**

`POST` **/user/signin**

### 2. React Client (Frontend)

Directory `client`

#### Features:

1. **Complete CRUD functionality**
    - Supports create, read, update, and delete (CRUD) operations for player cards.

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
