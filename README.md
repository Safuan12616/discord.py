# discord.py

A modern, easy to use, feature-rich and async ready API wrapper for Discord written in Pyhthon.

## Key Featurs

- Modern Pythonic API using ``async`` and ``await``.
- Proper rate limiting handling.
- Optimised in both speed and memory.

## Installing

**Python 3.8 or higher is requirment.**

To install library with full voice support, you can just run the following command:
```
# Linux/macOS
python -m pip install -U discord.py

# Windows
py -3 -m pip -U discord.py
```
Otherwise to get voice support you should run the following command:
```
# Linux/macOS
python3 -m pip install -U "discord.py[voice]"

# Windows
py -3 -m pip install -U discord.py[voice]
```

### Optional Packages

- [PyNaCl](https://pypi.org/project/PyNaCl/) (for voice support)

Please note that on Linux installing voice you must install the following packages via your favourite package manager (e.g. ``apt``, ``dnf``, etc) before running the above commands:
- libffi-dev (or ```libffi-devel``` on some systems)
- python-dev (e.g. ```python3.6-dev``` for Python 3.6)

## Quick Example

```py
import discord

class MyClient(discord.Client):
    async def on_ready(self):
        print('Logged on as', self.user)

    async def on_message(self, message):
        # don't respond to ourselves
        if message.author == self.user:
            return

        if message.content == 'ping':
            await message.channel.send('pong')

client = MyClient()
client.run('token')
```
### Bot Example
```py
import discord
from discord.ext import commands

bot = commands.Bot(command_prefix='>')

@bot.command()
async def ping(ctx):
    await ctx.send('pong')

bot.run('token')
```
You can find more example in examples direcotry.
