# real-world-vue

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

## Deplot instructions
Run `npm run build`
 
 Creates a dist directory
 - css
 - js
 - index.html

 Build files are auto-injected into the index.html (dependencies and app specific code)

### Deployment Plan
- Find a web hosting service
- Get SSL for a secure domain
- Build the site locally
- Drop those files into the server
- Ensure its served correctly

Can use render to manage deployment
- Create free account using github
- Click +New > Static Site
- Connect a repo via Github
- Give Render access to specific repo
- Complete site setup
- To Adjust for History Mode within Dashboard
  - Nav to Redirects/Rewrites
  - Add Rule
  - Source: /*
  - Desination: index.html
  - Action: Rewrite
  - Additional action -> need to implement a catch-all route within vue app to show a 404 when 404 error encountered.