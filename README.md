# J-Social-
`A full-stack social media app with login, posts, DM, likes. Node.js + MongoDB`
const express = require('express');
const cors = require('cors');
const bodyParser = require('body-parser');
const mongoose = require('mongoose');
const app = express();
const PORT = process.env.PORT || 3000;

app.use(cors());
app.use(bodyParser.json({limit: '10mb'}));
app.use(express.static('public'));

mongoose.connect(process.env.MONGODB_URI);

const User = mongoose.model('User', { username: String, phone: String, password: String, avatar: String });
const Post = mongoose.model('Post', { userId: String, username: String, avatar: String, text: String, image: String, likes: [String], comments: [], time: Date });

// AUTH
app.post('/api/signup', async (req,res)=>{ /*...same code from before... */ });
app.post('/api/login', async (req,res)=>{ /*... */ });
app.post('/api/reset', async (req,res)=>{ /*... */ });

// POSTS + DM + etc... paste all the routes from our last message here

app.listen(PORT, ()=>console.log(`🔥J Social running on ${PORT}`));
