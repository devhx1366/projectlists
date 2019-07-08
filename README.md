# projectlists

node -v
mongo -v

mkdir backend
npm init -y
npm i -S express body-parser bcryptjs jsonwebtoken

code-insider .

npm i g -D nodemon

npm i -S mongoose

touch server.js

mkdir auth
mkdir config

*server.js*
'use strict'
const express = require('express');
const app = express();

app.listen(3000,()=>console.log('server running on port 3000'));

npm run s

*auth.rountes.js*
const Users = require('./auth.controller');
module.exports = (router)=>{
router.post('./register',Users.createUser);
router.post('./login',Users.loginUser);
};

*auth.controller.js*
import User =required('./auth.dao');
const jwt = require('jasonwebtken');
const bcrypt = require('bcryptjs');
const SECRET_KEY = 'secretkey123456';
exports.creacteUser = (req,res,next)=>{
const newUser = {
  name: req.body.name,
  email:req.body.email,
  password:req.body.password,
  }
  User.create(newUSer,(err,user)=>{
  if(err)
  return res.status(500).send(server error);
  const expiresIn = 24*60*60;
  const accessToken = jwt.sign({idLuser.id},
  SECRET_KEY,{
  expiresIn: expiresIn});
  
  //response
  res.send({user});
  });
  
}

exports.loginUser = (req,res,next) =>
{
const userData = {
email:req.body.email,
password:req.body.password
}
User.findOne({email:userData.email},(err.user)=>{
if(err) return res.status(500).send('server error!');

if(!user){
res.staus(409).send({message:"something is wrong"});
}
else{
const resultPassword = userData.password;
if(resultPassword){
const expires
}}

})

*auth.dao.js*

*auth.moduel.js*




