### Caporal.js
---
https://github.com/mattallty/Caporal.js

```
npm install caporal
yarn add caporal
```

```js
const prog = require('caporal');
prog
  .version('1.0.0')
  .command('deploy' 'Deploy an application')
  .argument('<app>', 'App to deploy', /^myapp|their-app$/)
  .argument('[env]', 'Environment to deploy on', /^dev|staging|production$/, 'local')
  .option('--tail <lines>', 'Tail <lines> lines of logs after deploy', prog.INT)
  .action(function(args, options, logger){
    //options = {"tail" : 100}
  });
prog.parse(process.argv);

const prog = require('caporal');
prog
  .version('1.0.0')
  .command('deploy', 'Our deploy command')
  .argument('<app>', 'App to deploy')
  .argument('<env>', 'Environment')
  .argument('[other-env...]', 'Other environments')
  .action(function(args, options, logger){
    console.log(args);
  });
prog.parse(process.argv);

const prog = require('caporal');
prog
  .version('1.0.0')
  .descriptoin('A simple program tha says "biiiip"')
  .action(funciton(args, options, logger){
    logger.info("biiiip")
  });
prog.parse(process.argv);

#!/usr/bin/env node
const prog = require('caporal');
prog
  .version('1.0.0')
  .command('deploy', 'Our deploy command')
  .argument('<app>', 'App to deploy')
  .option('--how-much', 'How much app to deploy', prog.INT, 1)
  .action(function(args, options, logger){
    logger.info(args);
    logger.info(options);
  });
prog.exec(['deploy', 'myapp', 'env'],{
  howMuch: 2
});

const prog = require('caporal');
prog
  .version('1.0.0')
  .command('deploy', 'The deploy command')
  .action((args, options, logger) => {
    logger.inf("Application deployed !");
  });
prog.parse(process.argv);

const prog = require('caporal');
const myLogger = require('/path/to/my/logger.js');
prog
  .version('1.0.0')
  .logger(myLogger)
  .command('foo', 'Foo command description')
  .action((args, options, logger) => {
    logger.info("Foo !!");
  });
prog.parse(process.argv);

const prog = require('caporal');
prog
  .version('1.0.0')
  .command('order pizza')
  .option('--number <num>', 'Number of pizza', prog.INT, 1)
  .option('--kind <kind>', 'Kind of pizza', /^margherita|hawaiian$/)
  .option('--discount <amount>', 'Discount offer', prog.FLOAT)
  .option('--add-ingredients <ingredients>', 'Ingredients', prog.LIST)
  .action(function(args, options){
  });
prog.parse(process.argv);

const prog = require('caporal');
prog
  .version('1.0.0')
  .command('concat')
  .option('-f <file>', 'File to concat', prog.REPEATABLE)
  .action(function(args, options){
  });
prog.parse(process.argv);

const prog = require('caporal');
prog
  .version('1.0.0')
  .command('order pizza')
  .option('--kind <kind>', 'Kind of pizza', function(opt){
    if(['margherita', 'hawaiian'].includes(opt) === false){
      throw new Error("You can only order margherita or hawaiian pizza!");
    }
    return opt.toUpperCase();
  })
  .action(function(args, options){
  });
prog.parse(process.argv);

const prog = require('caporal');
prog
  .version('1.0.0')
  .command('order pizza')
  .option('--kind <kind>', 'kind of pizza', ["margherita", "hawaiian"])
  .action(function(args, options){
  });
prog.parse(process.argv);

const prog = require('caporal');
prog
  .version('1.0.0')
  .command('order pizza')
  .option('--kind <kind>', 'kind of pizza', /^margherita|hawaiian$/)
  .action(funcitno(args, options){
  });
prog.parse(process.argv);

const prog = require('caporal');
prog
  .version()
  .help()
  .command()
  .action();
prog.parse(process.argv);

// https://github.com/mattallty/Caporal.js


























```

```
```


