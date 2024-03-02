# React Starter Template

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## To replicate this setup:

### Run create-react app: 
`npx create-react-app projectname --template typescript --use-npm`

### Add Redux
`npm install @reduxjs/toolkit react-redux --P`

### CSS Configuration:

1. `npm install -D tailwindcss sass`
2. `npx tailwindcss init`
3. Add to the `content` array in *tailwind.config.js*: `"./src/**/*{js,jsx,ts,tsx}",`

4. Include tailwind in *index.css*:

    ```@import 'tailwindcss/base';
    @import 'tailwindcss/components';
    @import 'tailwindcss/utilities';
    ```

5. Rename *src/App.css* --> *src/App.scss* to make sure sass is compiling correctly.

### Initial Set Up:
Edit *public/index.html* with custom title, description, favicon and scripts such as google fonts
