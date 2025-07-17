mkdir socketio-chat
cd socketio-chat
mkdir client server
cd client
npm init -y
npm install react react-dom react-scripts socket.io-client
cd ../server
npm init -y
npm install express socket.io mongoose
const express = require('express');
const app = express();
const server = require('http').createServer(app);
const io = require('socket.io')(server);
const mongoose = require('mongoose');

mongoose.connect('mongodb:                                                                                 

app.use(express.static('//localhost/socketio-chat', { useNewUrlParser: true, useUnifiedTopology: true });

app.use(express.static('public'));

io.on('connection', (socket) => {
  console.log('a user connected');

                              
});

server.listen(3001, () => {
  console.log('// Handle socket events here
});

server.listen(3001, () => {
  console.log('Server listening on port 3001');
});

import React, { useState, useEffect } from 'react';
import io from 'socket.io-client';

const socket = io('http:                   

function App() {
  const [message, setMessage] = useState('//localhost:3001');

function App() {
  const [message, setMessage] = useState('');
  const [messages, setMessages] = useState([]);

  useEffect(() => {
    socket.on('connect', () => {
      console.log('Connected to the server');
    });

    socket.on('disconnect', () => {
      console.log('Disconnected from the server');
    });
  }, []);

  const handleSendMessage = () => {
    socket.emit('message', message);
    setMessage('');
  };

  return (
    <div>
      <input type="text" value={message} onChange={(e) => setMessage(e.target.value)} />
      <button onClick={handleSendMessage}>Send</button>
      <ul>
        {messages.map((message, index) => (
          <li key={index}>{message}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;
