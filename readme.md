## How to run locally
 
 - `npm install`
 - install python requirements:
 - - `cd src/StoVaCore`
 - - `pip install -r requirements.txt`
 - `npm start` (it will open webpack dashboard and browser)
 - in `src/main_electron.js` make sure that `win.loadURL` loads `http://localhost:3000/`
 - `npm run start-electron`
 - electron main proccess will start python proccess (`src/StoVaCore/wallet_api.py`) on 5000 port.


## How to make a build

### Prepare enviroment (Ubuntu example)
 - `apt install python3-pip`
 - `pip3 install -r requirements.txt` for StoVaCore repo
 - `apt-get install curl software-properties-common`
 - `curl -sL https://deb.nodesource.com/setup_11.x | sudo -E bash -` (to install nodejs v11)
 - `sudo apt-get install -y nodejs`
 - `npm install`
 - `npm rebuild node-sass` (as it's platform-dependent)

### Make a build
 - - make python build: `pyinstaller -F wallet_api.py` (result will appear in `src/StoVaCore/dist`)
 - `npm run electron-build:linux`
 - builded application will appear in `dist` folder

### Install Linux build
 - `sudo dpkg -i paste-wallet_1.0.0_amd64.deb`
 - if there are any uninstalled dependencies - run `sudo apt -f install`
 - Run `pastel-wallet` from command line

## Logging
 - For development run all logs will appear in the terminal
 - For packaged run logs path depends on the operation system. For OS X it is `/Users/<currentUser>/Library/Logs/pastel-wallet/log.log`
