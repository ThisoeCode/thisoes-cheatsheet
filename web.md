> ## Menu
>
> [jQuery](#jquery)
>
> [npm and nextjs](#npm)
>
> [Maven (Java)](#maven)
>
> [Composer (PHP)](#composer)
>



# jQuery
[jQuery code RAW (min)](https://code.jquery.com/jquery-latest.min.js)

## CDNs
```html
<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
```

## cheatsheet
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

### Modify version **_after committed_**
```bat
npm version 0.1.7
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