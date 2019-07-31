# Setting up Tailwind and PostCSS

### `npm init -y`
### `npm install tailwindcss postcss-cli autoprefixer`

## Then, generate a tailwind.config.js file:

### `npx tailwind init`

## Next, create a postcss.config.js file:

`module.exports = {
  plugins: [
    require('tailwindcss'),
    require('autoprefixer'),
  ]
}`

## Now create a CSS file and add the special @tailwind directives:

`@tailwind base;
@tailwind components;
@tailwind utilities;`

## Add a simple build script to your package.json file to compile your CSS:
`{
  // ...
  "scripts": {
    "build": "postcss css/tailwind.css -o public/build/tailwind.css"
  },
  // ...
}`

## Run your build script to generate your CSS:

### `npm run build`

## Create a simple HTML file that includes your compiled CSS:

`<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
  <link rel="stylesheet" href="/build/tailwind.css">
</head>
<body>
  <h1 class="text-4xl font-bold text-center text-blue-500">Hello world!</h1>
</body>
</html>`