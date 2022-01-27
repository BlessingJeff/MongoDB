1.Find all the information about each products

db.data.find({}).pretty()

2.Find the product price which are between 400 to 800

db.data.find({product_price:{$gte:400,$lte:800}}).sort({product_price:1}).pretty()

3.Find the product price which are not between 400 to 600

db.data.find({product_price:{$not:{$gte:400,$lte:800}}}).sort({product_price:1}).pretty()

4.List the four product which are grater than 500 in price 

db.data.find({product_price:{$gt:500}}).sort({product_price:1}).limit(4).pretty()

5.Find the product name and product material of each products

db.data.find({},{product_name:1,product_material:1,_id:0}).sort({product_price:1}).pretty()

6.Find the product with a row id of 10

db.data.find({id:"10"}).pretty()

7.Find only the product name and product material

db.data.find({},{product_name:1,product_material:1,_id:0}).sort({product_price:1}).pretty()

8.Find all products which contain the value of soft in product material 

db.data.find({product_material:{$eq:"Soft"}}).sort({product_price:1}).pretty()

9.Find products which contain product color indigo  and product price 492.00

db.data.find({ $or: [{ product_color: "indigo" }, { product_price:492 }] }).pretty()

10.Delete the products which product price value are same

db.data.aggregate([{$group:{_id:{product_price:"$product_price"},count:{$sum:1}}},{$match: {count: 2}}])




