# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)

### uml diagram
![uml](./uml.png)

```plantuml
@startuml uml
    !include ./uml.puml
@enduml
```

```plantumlcode
@startuml uml
    rectangle project {
    folder "/node_modules" as project_node_modules {
        node "/..." as project_packages
    }
    folder "/src/..." as project_src {
        file "*.js" as project_js
        file "*.css" as project_css
        file "logo.svg" as project_logo
    }
    folder "/public/..." as project_public {
        file "index.html" as project_index
        file "/favicon.ico" as project_favicon
        file "/logo192.png" as project_logo192
        file "/manifest.json" as project_manifest
    }
}

card localhost:3000 {
    file "index.html" as build_index #geen 
    file "/favicon.ico" as build_favicon
    file "/logo192.png" as build_logo192
    file "/manifest.json" as build_manifest
    file "/static/js/bundle.js" as build_bundle
    file "/static/js/vendor~main.chunk.js" as build_vendor
    file "/static/js/main.chunk.js" as build_main
    file "/static/media/logo.svg" as build_logo

    build_index <-- build_favicon:link
    build_index <-- build_logo192:link
    build_index <-- build_manifest:link
    build_index <-r- build_bundle:script
    build_index <-- build_vendor:script
    build_index <-- build_main:script
    build_index <-- build_logo:img
}

    build_vendor <-- project_packages 
    build_main <-- project_js
    build_logo <-- project_logo
    build_index <-- project_css
    ' файл "public/index.html" - шаблон для "index.html"
    build_index <-- project_index
    build_favicon <-- project_favicon
    build_logo192 <-- project_logo192
    build_manifest <-- project_manifest
@enduml
```

