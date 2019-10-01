A quick test to how config vars get required in Create React Apps

First create the app:
```
npx create-react-app my-app
cd my-app
```

Edit App.js to add variable:
```
<p>
  REACT_APP_NOT_SECRET_CODE={process.env.REACT_APP_NOT_SECRET_CODE}
</p>
...
```

Create git repo
```
git init .
```

Create Heroku app:
```
heroku create my-app
```

Add variable to Heroku app:
```
heroku config:set REACT_APP_NOT_SECRET_CODE="this is the value of an environment variable"
```

Update `yarn.lock` (not sure why I needed this):
```
yarn install
```

Push to Heroku:
```
git push heroku master
```

View app and see variable:
```
heroku open
```

![screenshot](https://raw.githubusercontent.com/chap/create-create-react-app-heroku-config/master/Screen%20Shot%202019-10-01%20at%202.35.26%20PM.png)
