# Mongodb Deprecation warning explanation 
**Deprecation** | **Value** | **Explanation**
------------|----------- | ---------------
useNewUrlParser | true | **parsing**: is the process of analyzing simple text and convert it into a more useful format 
useFindAndModify | false | by default mongodb allow findAndModify() **old methods** putting this to false to force the backend to stop using it and use the new methods FindOneAndUpdate()
useCreateIndex | true | ensureIndex() has been deprecated and CreateIndex() is the new version of creating an index for Data
useUnifiedTopology | true | The useUnifiedTopology option removes support for several connection options that are no longer relevant with the new topology engine [Handles monitoring servers]

Nodejs Mongodb configuration 
```javascript
//Connect to DB
mongoose.set('useNewUrlParser', true);
mongoose.set('useFindAndModify', false);
mongoose.set('useCreateIndex', true);
mongoose.set('useUnifiedTopology', true);
mongoose.connect(process.env.MONGODB_URL, (err) => {
    if (!err) {
        console.log('Mongodb has been connected correctly')
    } else {
        console.log(`Error from dataBase connection:${err}`);
    }
});
```
