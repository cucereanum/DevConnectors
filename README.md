# DevConnectors
It's an App to help you to connect with other developers

Preparing for production
For config dev files
1. New production.json (same values as in default.json)
2. package.json on server: "heroku-postbuild" : "NPM_CONFIG_PRODUCTION=false npm install --prefix client && npm run build --prefix client" 
3. on server.js,, delete app.get(/) if exists
4. load path module: if(process.env.NODE_ENV==='production') {
              app.use(express.static('client/build')); 
      app.get('*'. (req,res) => { 
      res.sendFile(path.resolve(__dirname, 'client', 'build', 'index.html'))
      }) 
      }
