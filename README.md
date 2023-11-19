# Inteligence
Discord Bot code
const Discord = require('discord.js');
const client = new Discord.Client();
const prefix = '!'; // Puedes cambiar el prefijo del comando aquí

client.on('ready', () => {
  console.log(`Bot está listo como ${client.user.tag}!`);
});

client.on('message', message => {
  if (message.author.bot) return;
  if (!message.content.startsWith(prefix)) return;

  const args = message.content.slice(prefix.length).trim().split(/ +/);
  const command = args.shift().toLowerCase();

  if (command === 'ping') {
    message.channel.send('¡Pong!');
  } else if (command === 'saludo') {
    message.channel.send(`¡Hola, ${message.author.username}!`);
  }
  // Agrega más comandos aquí con más 'else if' o usa un 'switch'
});

const token = 'TU_TOKEN'; // Reemplaza 'TU_TOKEN' con el token de tu bot
client.login(token);
