# Level Customization Guide

This guide explains how to add, remove, or modify levels in your Connections game.

## Understanding the Level Structure

The game's levels are defined in [`game-data.json`](game-data.json). Each level contains:

- **level**: A unique number (1, 2, 3, etc.)
- **name**: A descriptive name for the level difficulty
- **categories**: An array of 4 word groups, each containing:
  - **theme**: The hidden theme that connects the 4 words
  - **words**: An array of exactly 4 words/phrases
  - **difficulty**: Optional field for your reference (easy, medium, hard)

## Adding New Levels

### Step 1: Open the JSON File
Edit [`game-data.json`](game-data.json) in any text editor.

### Step 2: Add Your Level
Add a new level object to the `levels` array. Here's the template:

```json
{
  "level": 5,
  "name": "Your Level Name",
  "categories": [
    {
      "theme": "Your Theme 1",
      "words": ["WORD1", "WORD2", "WORD3", "WORD4"],
      "difficulty": "easy"
    },
    {
      "theme": "Your Theme 2", 
      "words": ["WORD5", "WORD6", "WORD7", "WORD8"],
      "difficulty": "medium"
    },
    {
      "theme": "Your Theme 3",
      "words": ["WORD9", "WORD10", "WORD11", "WORD12"],
      "difficulty": "medium"
    },
    {
      "theme": "Your Theme 4",
      "words": ["WORD13", "WORD14", "WORD15", "WORD16"],
      "difficulty": "hard"
    }
  ]
}
```

### Step 3: Update Level Numbers
Make sure level numbers are sequential (1, 2, 3, 4, 5...).

### Example: Adding Level 5
```json
{
  "level": 5,
  "name": "Master",
  "categories": [
    {
      "theme": "Types of Birds",
      "words": ["EAGLE", "ROBIN", "SPARROW", "CARDINAL"],
      "difficulty": "easy"
    },
    {
      "theme": "Programming Languages",
      "words": ["PYTHON", "JAVASCRIPT", "JAVA", "RUBY"],
      "difficulty": "medium"
    },
    {
      "theme": "Things That Fly",
      "words": ["AIRPLANE", "BUTTERFLY", "DRONE", "KITE"],
      "difficulty": "medium"
    },
    {
      "theme": "Words with 'IGHT'",
      "words": ["LIGHT", "NIGHT", "SIGHT", "BRIGHT"],
      "difficulty": "hard"
    }
  ]
}
```

## Removing Levels

### Option 1: Delete Entire Level
Simply remove the level object from the `levels` array and renumber remaining levels.

### Option 2: Replace Level Content
Keep the level number but change the name and categories completely.

## Modifying Existing Levels

### Change Level Name
Update the `name` field:
```json
"name": "Super Expert"
```

### Change Categories
Replace any of the 4 category objects with new themes and words:
```json
{
  "theme": "New Theme",
  "words": ["NEW1", "NEW2", "NEW3", "NEW4"],
  "difficulty": "medium"
}
```

### Change Individual Words
Update specific words in the `words` array, keeping exactly 4 words per category.

## Important Rules

### ✅ Do's
- **Always use exactly 4 categories per level**
- **Always use exactly 4 words per category**
- **Keep level numbers sequential (1, 2, 3...)**
- **Use descriptive theme names**
- **Test your connections to ensure they make sense**

### ❌ Don'ts
- **Don't use the same word in multiple categories within a level**
- **Don't skip level numbers (e.g., 1, 2, 4, 5)**
- **Don't use more or fewer than 4 words per category**
- **Don't use more or fewer than 4 categories per level**

## Theme Ideas

### Easy Themes
- Colors
- Animals
- Food items
- Common objects
- Body parts

### Medium Themes
- Movie genres
- Countries
- Sports
- Professions
- Transportation

### Hard Themes
- Words starting/ending with specific letters
- Words with double letters
- Things that share a property (e.g., "Things with wheels")
- Pop culture references
- Abstract connections

## Testing Your Changes

1. **Save the JSON file**
2. **Open or refresh [`index.html`](index.html) in your browser**
3. **Play through your new/modified levels**
4. **Check that all connections make logical sense**
5. **Verify level progression works correctly**

## JSON Validation

Make sure your JSON is valid:
- Use double quotes around all strings
- Include commas between array items and object properties
- Don't add trailing commas
- Maintain proper bracket/brace matching

## Example: Complete 5-Level Structure

```json
{
  "levels": [
    {
      "level": 1,
      "name": "Beginner",
      "categories": [...]
    },
    {
      "level": 2, 
      "name": "Intermediate",
      "categories": [...]
    },
    {
      "level": 3,
      "name": "Advanced", 
      "categories": [...]
    },
    {
      "level": 4,
      "name": "Expert",
      "categories": [...]
    },
    {
      "level": 5,
      "name": "Master",
      "categories": [...]
    }
  ]
}
```

The game will automatically detect and support any number of levels you add to the JSON file!