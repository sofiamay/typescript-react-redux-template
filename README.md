# React Starter Template

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## To replicate this setup:

### Run create-react app: 
`npx create-react-app projectname --template typescript --use-npm`

### Add Redux
`npm install @reduxjs/toolkit react-redux --P`

### CSS Configuration:

1. `npm i tailwindcss postcss-cli autoprefixer -D` and `npm install sass`
2. `npx tailwindcss init`
3. Add to the `content` array in *tailwind.config.js*: `"./src/**/*{js,jsx,ts,tsx}",`
4. `touch postcss.config.js` and add: 
```
module.exports = {
  plugins: [require("tailwindcss"), require("autoprefixer")]
};
```
5. Create a *styles/* directory. Create *styles/tailwind.scss* in this directory. Move index.css to this directory and rename it to *index.scss*. In *index.tsx*, update the reference to *./styles/index.scss*

6. Include in in *tailwind.scss*:

    ```
    @import 'tailwindcss/base';
    @import 'tailwindcss/components';
    @import 'tailwindcss/utilities';
    ```

7. Update *package.json* with these scripts:
```
"scripts": {
    "start": "npm run build:css && react-scripts start",
    "build": "npm run build:css && react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "build:css": "postcss src/styles/tailwind.scss -o src/styles/index.scss "
  }
```

8. Rename *src/App.css* --> *src/App.scss* to make sure sass is compiling correctly.  Edit */src/App.tsx* to import the new version.

9. (*Optional*): Use CSS template
Update *src/index.css* with preferred CSS template

### Add directories/files:
1. Add *src/components/*, *src/hooks/*, and *src/store/index.ts*

2. Update *src/store/index.ts* with:

    ```
    import { configureStore } from "@reduxjs/toolkit";

    export const store = configureStore({
        reducer: {},
    });
    ```
    
3. Update *src/index.tsx* to use store:

    ```
    import { Provider } from 'react-redux';
    import { store } from './store';
    ...
    root.render(
        <React.StrictMode>
            <Provider store={store}>
            <App />
            </Provider>
        </React.StrictMode>
        );
    ```

