# MtgCard.DB
This repo is currently the instructions on converting mtgJson files to a format that MongoDB can handle. Eventually I hope to automate this process into a single-step process for updating a MongoDB collection.

## Process
1. Clone https://github.com/mtgjson/mtgcsv.git
```
git clone https://github.com/mtgjson/mtgcsv.git
```

2. Install and Run mtgcsv
```
npm install
node generate.js
```

3. Import the resulting CSV(s) into your MongoDB
```
mongoimport -h <HOSTNAME>:<PORT> -d <DATABASE> -c <COLLECTION> -u <USERNAME> -p <PASSWORD> --type csv --headerline --file <FILENAME>
```
