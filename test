
const mongoose = require('mongoose');

mongoose.connect("mongodb://localhost:27017/fruitDB")

const fruitsSchema = new mongoose.Schema({
    name: {
        type: String,
    },
    rating: {
        type: Number,
        min: 1,
        max: 5
    },
    review: String
});

const Fruit = mongoose.model("Fruit", fruitsSchema);

const fruit = new Fruit({
    rating: 4,
    review: "So much sweet!"
});

//fruit.save();

const personSchema = new mongoose.Schema({
    name: String,
    age: Number,
    favFruit: fruitsSchema
});

const Person = mongoose.model("Person", personSchema);

const mango = new Fruit({
    name: "Mango",
    rating: 3,
    review: "Decent taste!"
});

mango.save();

// const person = new Person({
//     name: "Amy",
//     age: 17,
//     favFruit: pear
// });

// person.save();

Person.updateOne({name: "John"}, {favFruit: mango}, (err, res)=>{
    if(err){
        console.log(err);
    }else{
        console.log(res);
    }
});


const kiwi = new Fruit({
    name: "Kiwi",
    rating: 3,
    review: "I new taste for me!"
});

const banana = new Fruit({
    name: "Banana",
    rating: 5,
    review: "I liked it very much!"
});

const orange = new Fruit({
    name: "Orange",
    rating: 4,
    review: "Its very tasty."
});

//Fruit.insertMany([kiwi, orange, banana]);



Fruit.find().then(function (fruits) {

    fruits.forEach(function (fruit) {
        console.log(fruit.name);
    });
    setTimeout(() => {
        mongoose.connection.close();
    }, 10);

    

});


//Fruit.updateOne({ $_id: '65c7341eddd361ae96f37009'}, { name: "Peach" });
