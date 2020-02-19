# DiscordSweep
> A simple (dirty) script to remove all of your Discord messages sent in a specified server.

Unfortunately, Discord does not offer a function to remove all user data from a server; even upon
account deletion any messages you sent in a server will persist. This program will search a
server for every message you sent (in all channels) and delete each one. This will not work for
private messages.

NOTE (!!!):
Running this script will (probably) break Discord's TOS against self-botting. So it should really
only be used if you're wanting to delete your account, are in fear of getting doxxed, etc.

## Installation
DiscordSweep requires a working Python3 installation. If you don't have one, head over here and
install it (https://www.python.org/downloads/). Next, clone the repo and install the dependencies:
```
git clone https://github.com/jamesfoxdev/DiscordSweep.git
cd DiscordSweep
pip3 install -r requirements.txt
```

## Gather required information
Three pieces of data are needed in order for DiscordSweep to do its job
1. The ID of the server to delete the messages from (18 numbers)
2. Your unique Discord user ID (18 numbers)
3. A valid Discord authorization token (upper and lowercase letters mixed with dashes and periods)

#### To find the server ID:
1. Right click on the server you want to delete the messages from in the server browser
2. Click `Copy ID`

#### To find your user ID:
1. Right click on your user on the users panel
2. Click `Copy ID`

#### To find a valid authorization token
The easiest way to retrieve an authorization token is through inspecting Discord XHR calls:
1. In the Discord GUI window hit `CTRL`+`SHIFT`+`I`
2. Navigate to the `Network` tab
3. Reload Discord by hitting `CTRL`+`R`
4. The table in the `Network` tab should now be populated, click on any entry on the list
5. On the right panel select the `Headers` tab
6. Scroll down to `Request Headers`
7. Select and copy the value associated with the `authorization` header. It should look something like this `JjUyNscxMDcwOTYyNDY2ODE2.Xkx-fw.xUw6yKF-AtbTQJviz0OG5xvmvik`

Once you have the three pieces: server ID, user ID and an authorization token you can proceed.

## Usage
```
usage: discordsweep.py [-h] [-c CAP] serverID userID authToken

positional arguments:
  serverID           Server ID to wipe from
  userID             Your Discord user ID
  authToken          Discord authorization token

optional arguments:
  -h, --help         show this help message and exit
  -c CAP, --cap CAP  Cap the amount of messages deleted to a server
```

## Roadmap
- Add support for Discord PM deletion
- More complex filters such as date/time

## License
MIT