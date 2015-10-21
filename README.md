# M102-MONGODB-FOR-DBAS
M102: MONGODB FOR DBAS

## HOMEWORK: HOMEWORK 1.1

Download and install MongoDB from www.mongodb.org. Then run the database as a single server instance on your PC (that is, run the mongod binary). Then, run the administrative shell. 

From the shell prompt type

## db.isMaster().maxBsonObjectSize 
 
at the ">" prompt.

What do you get as a result?

### Ans. 16777216

## HOMEWORK: HOMEWORK 1.2

Download the handout. Take a look at its content.

Now, import its contents into MongoDB, into a database called "pcat" and a collection called "products". Use the mongoimport utility to do this.

When done, run this query in the mongo shell:

db.products.find( { type : "case" } ).count()
What's the result?

### Ans. 3

## HOMEWORK: HOMEWORK 1.3

At this point you should have pcat.products loaded from the previous step. You can confirm this by running in the shell:

db.products.find()
// or:
db.products.count()
// should print out "11"
Now, what query would you run to get all the products where brand equals the string “ACME”?

### Ans.  db.products.find({"brand":"ACME"})

## HOMEWORK: HOMEWORK 1.4

How would you print out, in the shell, just the the value in the "name" field, for all the product documents in the collection, without extraneous characters or braces, sorted alphabetically, ascending? (Check all that would apply.)


var c = db.products.find( { } ).sort( { name : -1 } ); while( c.hasNext() ) { print( c.next().name); }
var c = db.products.find( { }, { name : 1, _id : 0 } ).sort( { name : 1 } ); while( c.hasNext() ) { print( c.next().name); }
db.products.find( { }, { name : 1, _id : 0 } ).sort( { name : 1 } )
var c = db.products.find( { } ).sort( { name : 1 } ); c.forEach( function( doc ) { print( doc.name ) } );

### Ans.  
B - var c = db.products.find( { }, { name : 1, _id : 0 } ).sort( { name : 1 } ); while( c.hasNext() ) { print( c.next().name); }
D - var c = db.products.find( { } ).sort( { name : 1 } ); c.forEach( function( doc ) { print( doc.name ) } );

