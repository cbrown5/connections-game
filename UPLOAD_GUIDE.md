# Upload Custom Game Data - User Guide

## Overview

The Word Match Game now supports uploading custom game data via drag-and-drop or file browsing. This allows you to create personalized puzzles without modifying the game files directly.

## How to Upload Custom Data

### Method 1: Drag and Drop
1. Open the game in your browser (`index.html` or `forage-fish.html`)
2. Prepare your custom JSON file (see format below)
3. Drag the JSON file onto the **"Upload Custom Game Data"** zone
4. The game will validate and load your custom data automatically

### Method 2: Browse for File
1. Open the game in your browser
2. Click on the **"Upload Custom Game Data"** zone
3. Select your JSON file from the file browser
4. The game will validate and load your custom data

## JSON File Format

Your JSON file must follow this exact structure:

```json
{
  "levels": [
    {
      "level": 1,
      "name": "Level Name",
      "categories": [
        {
          "theme": "Category Theme 1",
          "words": ["Word1", "Word2", "Word3", "Word4"],
          "difficulty": "easy"
        },
        {
          "theme": "Category Theme 2",
          "words": ["Word5", "Word6", "Word7", "Word8"],
          "difficulty": "medium"
        },
        {
          "theme": "Category Theme 3",
          "words": ["Word9", "Word10", "Word11", "Word12"],
          "difficulty": "hard"
        },
        {
          "theme": "Category Theme 4",
          "words": ["Word13", "Word14", "Word15", "Word16"],
          "difficulty": "very hard"
        }
      ]
    }
  ]
}
```

## Validation Rules

Your uploaded JSON file will be validated against these rules:

### Required Structure
- ✅ Must have a `levels` array with at least one level
- ✅ Each level must have a `level` number (integer)
- ✅ Each level must have a `name` (string)
- ✅ Each level must have exactly **4 categories**

### Category Requirements
- ✅ Each category must have a `theme` (string)
- ✅ Each category must have exactly **4 words** (array of strings)
- ✅ The `difficulty` field is optional but recommended

### Common Validation Errors
- ❌ **"Missing or empty levels array"** - Your JSON must include a `levels` array
- ❌ **"Must have exactly 4 categories"** - Each level needs exactly 4 categories
- ❌ **"Must have exactly 4 words"** - Each category needs exactly 4 words
- ❌ **"All words must be strings"** - Words cannot be numbers or other types

## Example Custom Data

Here's a complete example with two levels:

```json
{
  "levels": [
    {
      "level": 1,
      "name": "Tech Terms",
      "categories": [
        {
          "theme": "Programming Languages",
          "words": ["Python", "JavaScript", "Java", "Ruby"],
          "difficulty": "easy"
        },
        {
          "theme": "Web Browsers",
          "words": ["Chrome", "Firefox", "Safari", "Edge"],
          "difficulty": "medium"
        },
        {
          "theme": "Database Systems",
          "words": ["MySQL", "PostgreSQL", "MongoDB", "Redis"],
          "difficulty": "hard"
        },
        {
          "theme": "Cloud Providers",
          "words": ["AWS", "Azure", "Google Cloud", "DigitalOcean"],
          "difficulty": "very hard"
        }
      ]
    },
    {
      "level": 2,
      "name": "General Knowledge",
      "categories": [
        {
          "theme": "Fruits",
          "words": ["Apple", "Banana", "Orange", "Grape"],
          "difficulty": "easy"
        },
        {
          "theme": "Colors",
          "words": ["Red", "Blue", "Green", "Yellow"],
          "difficulty": "easy"
        },
        {
          "theme": "Planets",
          "words": ["Mars", "Venus", "Jupiter", "Saturn"],
          "difficulty": "medium"
        },
        {
          "theme": "Musical Instruments",
          "words": ["Guitar", "Piano", "Drums", "Violin"],
          "difficulty": "hard"
        }
      ]
    }
  ]
}
```

## Tips for Creating Puzzles

1. **Start Simple**: Begin with obvious connections for easy categories
2. **Increase Difficulty**: Use subtle connections for harder categories
3. **Avoid Overlaps**: Make sure words clearly belong to only one category
4. **Test Your Puzzle**: Upload and play through to ensure it's solvable
5. **Use Themes**: Pick themes that make sense to your audience

## Difficulty Levels

The `difficulty` field supports these values:
- `"easy"` - Blue background when revealed
- `"medium"` - Cyan background when revealed  
- `"hard"` - Yellow background when revealed
- `"very hard"` - Orange background when revealed

## After Upload

When you successfully upload a file:
- ✅ You'll see a success message: "Successfully loaded X level(s)!"
- ✅ The game automatically resets to Level 1 with your new data
- ✅ All progress from the previous game is cleared
- ✅ You can upload a new file at any time to replace the current data

## Reverting to Original Data

To go back to the original game data:
1. Refresh the page (F5 or Ctrl+R)
2. The game will reload with the default `game-data.json` or `game-data-forage-fish.json`

## Troubleshooting

### Upload Not Working
- Make sure your file has a `.json` extension
- Check that your JSON is properly formatted (use a JSON validator)
- Verify all required fields are present

### Validation Errors
- Read the error message carefully - it will tell you exactly what's wrong
- Common issues: wrong number of words, missing fields, wrong data types
- Use the example above as a template

### Browser Compatibility
This feature works in all modern browsers that support:
- File API
- FileReader API
- Drag and Drop API

## Privacy & Security

- ✅ All file processing happens **locally in your browser**
- ✅ Your custom data is **never uploaded to any server**
- ✅ Files are only read from, never written to your computer
- ✅ Your custom data persists only until page reload

## Multiple Game Versions

Both game versions support the upload feature:
- **index.html** - Main game version (uses `game-data.json`)
- **forage-fish.html** - Forage fish themed version (uses `game-data-forage-fish.json`)

Each can load custom data independently.
