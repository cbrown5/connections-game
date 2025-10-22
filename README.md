# Word Match game

Emulation of the NYT connection game, implemented in javascript and html. Built with generative AI and the Roo Code AI Agent. 

Made as a fun way to quiz my students. See [an example here](https://www.seascapemodels.org/connections-game/). 

This game has multiple levels you play through. See `LEVEL_CUSTOMIZATION_GUIDE.md` for how to modify the data and the levels. 

## Upload Custom Game Data 

You can make your own game with minimal coding with a drag and drop interface.

Got to [this version](https://www.seascapemodels.org/connections-game/word-match-upload.html). 

You can then **drag and drop your own JSON data file** directly into the browser to create custom puzzles. No need to modify files - just prepare your JSON file and drop it onto the game. See `UPLOAD_GUIDE.md` for detailed instructions.

### Quick Start with Custom Data
1. Open `index.html` in your browser
2. Drag and drop your custom JSON file onto the upload zone
3. Play with your custom words and categories!

## Using the Game

To use just fork this repo, modify `game-data.json` then turn your repo into a github pages to serve it. 

If serving locally use: 

```
python3 -m http.server 8000
```

If you load `index.html` directly `fetch()` won't work and it will use the default data hard coded into index.html. Github pages doesn't have this problem. 





