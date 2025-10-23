# Word Match game

Emulation of the NYT connection game, implemented in javascript and html. Built with generative AI and the Roo Code AI Agent. 

Made as a fun way to quiz my students. See [an example here](https://www.seascapemodels.org/connections-game/). 

This game has multiple levels you play through. See `LEVEL_CUSTOMIZATION_GUIDE.md` for how to modify the data and the levels. Read on below for a version where you can upload your own game data directly to the webpage. 

## Using the Game

To use just fork this repo, modify `game-data.json` then turn your repo into a github pages to serve it. 

If serving locally use: 

```
python3 -m http.server 8000
```

If you load `index.html` directly `fetch()` won't work and it will use the default data hard coded into index.html. Github pages doesn't have this problem. 

## Upload Custom Game Data 

You can make your own game with minimal coding with a drag and drop interface.

Got to [this version](https://www.seascapemodels.org/connections-game/word-match-upload.html). 

You can then **drag and drop your own JSON data file** directly into the browser to create custom puzzles. No need to modify files - just prepare your JSON file and drop it onto the game. 

### Quick Start with Custom Data
1. Create a `mydata.json` or `mydata.txt` file on your computer, e.g. with a text editor. 
1. Open `index.html` in your browser
2. Drag and drop your custom JSON or .txt file onto the upload zone
3. Play with your custom words and categories!

### How to make game-data.JSON

Make sure your JSON is valid:
- Use double quotes around all strings
- Include commas between array items and object properties
- Don't add trailing commas
- Maintain proper bracket/brace matching

#### Example: Complete 4-Level Structure

```json
{
  "levels": [
    {
      "level": 1,
      "name": "Warm-up",
      "categories": [
        {
          "theme": "Shades of Blue",
          "words": ["Steel", "Azure", "Aqua", "Sky"],
          "difficulty": "easy"
        },
        {
          "theme": "Types of degree",
          "words": ["Diploma", "Bachelor", "Masters", "Honours"],
          "difficulty": "medium"
        },
        {
          "theme": "Things with propellers",
          "words": ["Plane", "Helicopter", "Ship", "Fan"],
          "difficulty": "hard"
        },
        {
          "theme": "Tasmanian marsupials",
          "words": ["Bandicoot", "Bettong", "Pademelon", "Potoroo"],
          "difficulty": "very hard"
        }
      ]
    },
    {
      "level": 2,
      "name": "Test 1",
      "categories": [
        {
          "theme": "Upwelling systems",
          "words": ["Humbolt", "Bonney", "Benguela", "Somali"],
          "difficulty": "easy"
        },
        {
          "theme": "Seabird families",
          "words": ["Procellariidae ", "Sulidae", "Laridae", "Spheniscidae"],
          "difficulty": "hard"
        },
        {
          "theme": "Marine mammal taxa",
          "words": ["Phocidae", "Otariidae", "Mysticeti", "Odontoceti"],
          "difficulty": "very hard"
        },
        {
          "theme": "Fishery ____",
          "words": ["Management", "Reference points", "Bycatch", "Discards"],
          "difficulty": "medium"
        }
      ]
    }
  ]
}
```

The game will automatically detect and support any number of levels you add to the JSON file. 


