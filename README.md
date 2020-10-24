# lights-out

Play the game at [https://lights-out.duanecreates.com](https://lights-out.duanecreates.com).  

## Documentation

### Play Instructions
Run ```yarn install``` and ```yarn serve``` in your terminal (in project root folder) and go to the localhost URL provided in the terminal.

### Components Structure
`App` takes care of wrapping the whole app.  
`Settings` wraps the top part, showing a slider which updates n (and grid) on slide.  
`Game` contains presentation of game grid and logic.  
`Switch` is a presentation component of each cell in the game's grid.  
`Win` simply shows a victorious message and prompts to play again.  

### Flow / Logic
Game starts with a default n of 5.  
The slider on top is to change the value of n.    
A grid gets generated consisting of n * n.  
Each cell has a state of on or off, reflected by its color.  
Once a grid cell has been clicked, the clicked element, and all four adjacent cells gets toggled.  
With every toggle, a check will be done to see if all the cells are off.  
If all the cells are off, a victorious message will be shown, prompting to play again, in which case would generate a new grid again.

### Testing
Tested in Chrome 86 and Firefox Developer Edition 83.

## Project setup
```
yarn install
```

#### Compiles and hot-reloads for development
```
yarn serve
```

#### Compiles and minifies for production
```
yarn build
```

#### Lints and fixes files
```
yarn lint
```

