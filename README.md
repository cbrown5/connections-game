# Connections game

Emulation of the NYT connection game, implemented in javascript and html. Built with generative AI and the Roo Code AI Agent. 

Made as a fun way to quiz my students. See [an example here](https://www.seascapemodels.org/connections-game/). 

This game has multiple levels you play through. See `LEVEL_CUSTOMIZATION_GUIDE.md` for how to modify the data and the levels. 

To use just fork this repo, modify `game-data.json` then turn your repo into a github pages to serve it. 

If serving locally use: 

```
python3 -m http.server 8000
```

If you load `index.html` directly `fetch()` won't work and it will use the default data hard coded into index.html. Github pages doesn't have this problem. 





