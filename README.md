import discord
import json
from discord.ext import commands

file = open('config.json', 'r')
config = json.load(file)

Bot = commands.Bot(config['prefix'])

@Bot.command(name='ping')
async def pings(ctx):
               await ctx.send(f'{ctx.author.mention}pong')


Bot.run(config['token'])
