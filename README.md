# Personal Portfolio

My personal portfolio website

[This project requirements](https://www.theodinproject.com/lessons/node-path-advanced-html-and-css-personal-portfolio)

[Live demo](https://minhhoccode111.github.io/personal-portfolio/)

[All my projects' live demos](https://minhhoccode111.github.io/all-projects-live-demos/)

## What I've learned

### Keep images' references between `html` files

When we generate a new `index.html` file in the `dist` directory base on the `template.html` file in the `src` directory using `html-webpack-plugin` and we want the reference of the images we use in `template.html` still work after generating `index.html` then we have to do like this:

```html
<!-- inside template.html file -->
<img src="<%= require('./path/from/template.html/to/image.png') %>" />
<!-- this image still work in index.html after generating -->
```

Configure in `webpack.config.js`

```jsx
// inside webpack.config.js
module: {
  rules: [
    {
      test: /\.(png|jpe?g|gif)$/i,
      type: 'asset/resource',
    },
  ],
},
output: {
  assetModuleFilename: 'assets/[hash][ext][query]',
}
```

### Tailwindcss

There are some bugs that make the classes I add to the element don't work and I have to add styles manually in `style.css`. And that mean some tools are just not perfect and we have to check it manually (or maybe I'm just bad and missing something ☹️)
