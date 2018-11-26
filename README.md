# Como usar?
* se debe instalar en el servidor de feathers: -> feathers-mongodb-fuzzy-search
`npm install feathers-mongodb-fuzzy-search --save`
* en el hook del modelo donde se quiere usar el fuzzy search debe estar configurado de la siguiente manera:
```javascript
    const search = require('feathers-mongodb-fuzzy-search');

    before: {
        all: [
        search(), // full text search on text indexes
        search({  // regex search on given fields
            fields: ['name']
        })
        ],
        find: [],
        get: [],
        create: [],
        update: [],
        patch: [],
        remove: []
    }
```
* en el cliente: debe estar configurado el servicio que sera enviado como parametro service al componente autocomplete (ejemplo con users) :

```javascript
     <search-autocomplete :service="`users`" label="Usuarios"></search-autocomplete>
```