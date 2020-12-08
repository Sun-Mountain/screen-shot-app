# About
As a learning exercise, I followed Free Code Camp's [How to Set Up a Real-World Project with Go and Vue](https://www.freecodecamp.org/news/how-i-set-up-a-real-world-project-with-go-and-vue/) tutorial.

# Set Up

Go into the folder `frontend` to set up the Vue frontend.

## Project setup
```
npm install
```

### Compiles and minifies for production
```
npm run build
```

This creates the `dist` folder that the go server will look for.

To run the full application, you will need get a token from [ScreenshotAPI](https://screenshotapi.net/). Put your token where it says `YOUR_PERSONAL_TOKEN_HERE`.

## Run the full application

```
go run main/server.go
```

# Future

I would like to add a loading animation feature to make the wait for the screenshot more bearable.