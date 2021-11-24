# ReferenceError-listen-is-not-defined-at-Object.-anonymous-
I am trying to install my SQL in a LInux's Docker, but when I finish my configuration i have the next error.

INDEX.JS

const express = require('express')
const app = express()

const pool = require('./database')

app.get('/products', async (req, res) => {
    try {
        // Get connection
        const conn = await pool.getConnection();

        // create a new query
        const query = 'select * from products';

        // executing the query
        const rows = await conn.query(query);

        //respond to the client
        res.status(200).json(rows);
    } catch (error) {
        console.log(error);
    }

});

app.post('/new-product', async (req,res)=> {
   console.log(req.body);
   
    // Get connection
    const conn = await pool.getConnection();

    // create a new query
    const query = 'INSERT INTO products SET ?';

    // executing the query
    const rows = await conn.query(query,req.body);

    //respond to the client
    res.status(200).json(resul);

})


app, listen(3000, () => {
    console.log('Server on port', 3000);
})

ERROR:

^

ReferenceError: listen is not defined
    at Object.<anonymous> (/home/alumno/Escritorio/mariadb-node-connection/index.js:43:1)
    at Module._compile (internal/modules/cjs/loader.js:999:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1027:10)
    at Module.load (internal/modules/cjs/loader.js:863:32)
    at Function.Module._load (internal/modules/cjs/loader.js:708:14)
    at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:60:12)
    at internal/main/run_main_module.js:17:47
