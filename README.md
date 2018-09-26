# makemeahanzi
Free, open-source Chinese character data

## Requirement
- Meteor
- mongodb(mongodump/mongorestore tools)


## Usage
1.Open http://localhost:3000/#{chinese} in browser, [like this](http://localhost:3000/#的).

2.Reload the database from the backup in the repository.
```
    Meteor.call('restore');
```

3.The "A" and "D" keys step back and forth between characters, while "shift-A" and "shift-D" step back and forth between incomplete characters. You can use the URL bar directly to add a new character (type it after the hash mark).

4.The "W" and "S" keys step up and down between different "stages". I organized the data generation workflow into a series of heuristic / ML algorithms, each of does one analysis and which can be overridden manually. Using the tool effectively requires knowing how these algorithms work and fail, though, since if you know one stage is probably going to be right, you can quickly scan it and move on.

5.Export data.  
```
    Meteor.call('export');
    // Check the Meteor logs and wait for dictionary.txt and graphics.txt to be ready

    Meteor.call('exportSVGs');
    // Check the Meteor logs and wait for .svgs to be ready
```
