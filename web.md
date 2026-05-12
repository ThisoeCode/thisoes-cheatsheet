## Menu

- [jQuery](#jquery)
- [npm and nextjs](#npm)
- [bun and hono](#bun)
- TODO: wrangler & CloudFlare Worker
- [Maven (Java)](#maven)
- [LAMP / cPanel related](#lamp)
- [Composer (PHP)](#composer)

*******



# jQuery
[jQuery code RAW (min)](https://code.jquery.com/jquery-latest.min.js)

### CDNs
```html
<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
```

### cheatsheet
```js
// document ready
$(_=>{
  // ...
})

// set a listener on dynamic generated elements
$('#a-static-parent').on('click','#the-dynamic-element',_=>{
  // ...
})

// find children and iterate
$(this).find('label').each(function(){
  $(this).attr('for', $(this).attr('for') + key)
})

// find parent
$(this).parent('#my-input').val()
```



*******



# npm
### Create new NextJS proj
```bat
:: `cd` to the directory where the proj root folder gonna stay in
npx create-next-app@latest
```

### NextJS preview & test on `localhost:3000`
```bat
npm run dev

npm run build
npm run start
```


## npm Package Management

### `npm init`
E.g.
```bat
npm init
:: package name: (@thisoe/acc_exe) @thisoe/acme.subtool
:: version: (1.0.0) 0.1.0
:: description: the sub-tool of acme project
:: entry point: (index.js) main.js
:: test command: 
:: git repository: https://github.com/ThisoeCode/acme.git
:: keywords: example, javascript
:: author: Thisoe
:: license: (ISC) MIT
:: type: (commonjs) module
```

### Update version of your package
Workflow: Keep Git working dir clean
```bat
git commit -am "hotfix"
npm version patch   :: 0.1.0 -> 0.1.1
npm version minor   :: 0.1.0 -> 0.2.0
npm version major   :: 0.1.0 -> 1.0.0
npm version 0.1.7
```
This automatically:
- updates `package.json` and `package-lock.json`
- creates a git commit
- creates a git tag



*******



# Bun

### Create new Hono-Bun proj

1. Init bun proj dir
```bat
bun init <THE_APP_NAME>
```

2. Make `bun start` and `bun dev`

Before `"devDependencies"` add:
```json

  "scripts": {
    "start": "bun index.ts",
    "dev": "bun --watch index.ts"
  },

```

3. Use Hono

```bat
bun i hono
```

```ts
// create file "hono.ts"
import { Hono } from 'hono'
import { logger } from 'hono/logger'

const app = new Hono()
app
  .use('*',logger())
  .get('/', c=>c.text('Hono!'))

export default app
```

```ts
// index.ts
import app from "./hono"

Bun.serve({
  fetch:app.fetch
})

console.log("Server is running.")
```



*******



# Maven
### clean hook
```bat
./mvnw clean
./mvnw clean <default-phases>
```

### [default]
```bat
./mvnw compile
./mvnw clean test
./mvnw clean package
./mvnw clean verify
```

### something like `npm run dev` on `localhost:8080`
```bat
./mvnw spring-boot:run
```



*******



# LAMP
### Thisoe's go-to root `.htaccess` settings
```apache
### BEGIN - Thisoe codes ###

Options +FollowSymLinks
RewriteEngine On

# Remove .php extension
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME}.php -f
RewriteRule ^([^\.]+)/?$ $1.php [NC,L]

# Remove .html extension
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME}.html -f
RewriteRule ^([^\.]+)/?$ $1.html [NC,L]

# If the request is for a directory
RewriteCond %{REQUEST_FILENAME} -d

# If index.php exists in the directory, serve it
RewriteCond %{REQUEST_URI} ^(.*)/$
RewriteCond %{DOCUMENT_ROOT}%1/index.php -f
RewriteRule ^(.*)/$ %{REQUEST_URI}index.php [L]

# If index.html exists in the directory, serve it
RewriteCond %{REQUEST_URI} ^(.*)/$
RewriteCond %{DOCUMENT_ROOT}%1/index.html -f
RewriteRule ^(.*)/$ %{REQUEST_URI}index.html [L]

### END - Thisoe codes ###
```

### In case a shared hosting won't spit `error_log` files for PHP errors
In needed PHP files:
```php
ini_set('log_errors', 1);
ini_set('error_log', __DIR__ . '/php-error.log');
```



*******



# Composer
### Add a package
```bat
composer require vlucas/phpdotenv
```

### Install all packages after pulling
```bat
composer install
```

### Show installed packages
```bat
composer show -i
```

### Uninstall a package
```bat
composer remove vlucas/phpdotenv
```
