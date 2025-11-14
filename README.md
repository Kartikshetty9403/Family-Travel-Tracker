📍 Family Travel Tracker

A full-stack Node.js + PostgreSQL application that allows users to track countries they’ve visited and visualize their travel journey on an interactive map.
Each family member has a unique profile, color theme, and a list of visited countries.

---------------------------------------------------------------------------------------

🚀 Features

👤 Add multiple family members

🌍 Track countries each user has visited

➕ Add new countries using a search input

🎨 Unique color theme per user

🗃️ PostgreSQL database for persistent storage

🔐 Environment variables to protect database credentials

--------------------------------------------------------------------------------------

🛠️ Tech Stack

Frontend: EJS, CSS
Backend: Node.js, Express.js
Database: PostgreSQL
Tools: Git, dotenv

--------------------------------------------------------------------------------------

✅ 📦 Installation & Setup Instructions (Full Guide)

Follow these steps to run the Family Travel Tracker project locally on your machine.

1️⃣ Clone the repository
git clone https://github.com/Kartikshetty9403/Family-Travel-Tracker.git
cd Family-Travel-Tracker

2️⃣ Install project dependencies

Make sure you have Node.js installed, then run:

npm install

3️⃣ Set up your PostgreSQL database
Step A — Create a new database

Open psql or PgAdmin and create a database named:

world

Step B — Create required tables

Run these SQL commands inside your database:

CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100),
  color VARCHAR(50)
);

CREATE TABLE countries (
  country_code VARCHAR(10) PRIMARY KEY,
  country_name VARCHAR(255)
);

CREATE TABLE visited_countries (
  id SERIAL PRIMARY KEY,
  user_id INTEGER REFERENCES users(id),
  country_code VARCHAR(10) REFERENCES countries(country_code)
);

Step C — Insert initial data (optional)
INSERT INTO users (name, color)
VALUES ('Jade', 'teal'),
       ('Jack', 'powderblue');
       
4️⃣ Create a .env file

Create a file named .env in the project root and add:

DB_USER=postgres
DB_HOST=localhost
DB_NAME=world
DB_PASSWORD=YOUR_PASSWORD_HERE
DB_PORT=5432   

5️⃣ Start the server

Run:

node index.js


You should see:

Server running on http://localhost:3000

6️⃣ Open the application

Visit:

👉 http://localhost:3000

You should now see the world map interface and user list.

🎉 You're all set!

The project is now running locally.

