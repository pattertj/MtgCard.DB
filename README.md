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

3. *(optional)* Open the resulting "csv" folder and copy out the list of file paths into Excel.
```
Ctrl+A within the "csv" folder
Shift+Right Click > "Copy as Path"
Ctrl+V into Excel
```

4. Build the mongoimport command
```
mongoimport -h <HOSTNAME>:<PORT> -d <DATABASE> -c <COLLECTION> -u <USERNAME> -p <PASSWORD> --type csv --headerline --file <FILENAME>
```
or, for bulk import using Excel in step #3 above
```
="mongoimport -h <HOSTNAME>:<PORT> -d <DATABASE> -c <COLLECTION> -u <USERNAME> -p <PASSWORD> --type csv --headerline --file "&""""&B2&""""
```

5. Open a Console and navigate to your MongoDB bin
```
cd "C:\Program Files\MongoDB\Server\3.6\bin"
```

6. Run the MongoImport command from step #4.
