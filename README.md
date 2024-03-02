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

6. (*Optional*): Use CSS template
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
    
3. Update *src/*index.ts* to use store:

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

