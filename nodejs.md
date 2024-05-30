https://tmapi.top/



Find all movies in the fantasy and drama genres: {genres : ["Drama", "Fantasy"]}

Find all the movies that have a runtime greater than 120 minutes: {runtime: {$gt: 120}}

https://www.mongodb.com/docs/v6.0/indexes/#indexes-and-collation

https://learn.mongodb.com/learn/course/mongodb-indexes/lesson-1-using-mongodb-indexes-in-collections/learn


https://intercom-help.mongodb.com/en/articles/7207806-how-to-generate-synthetic-data-with-the-movies-dataset


Create a Project Directory
mkdir node_quickstart
cd node_quickstart
npm init -y

mongo db driver 
npm install mongodb@6.6





// Define the associations
Customer.hasMany(Order);
Order.belongsTo(Customer);
Order.hasMany(Product);
This establishes a relationship where a Customer has many Orders, and each Order has many Products.

1 hasMany Relationship:

This relationship signifies that one entity (e.g., a user) can have many instances of another entity (e.g., posts).
For example, in a blogging application, a user can have many blog posts.
In Sequelize, the "hasMany" association can be defined between two models like this:


// User model
const User = sequelize.define('User', {
    // user attributes
});

// Post model
const Post = sequelize.define('Post', {
    // post attributes
});

// Define the association
User.hasMany(Post);

belongsTo Relationship:

This signifies a one-to-one or many-to-one relationship where one entity (e.g., a post) belongs to another entity (e.g., a user).
For example, in a blogging application, a post belongs to a single user who authored it.
In Sequelize, you can define a "belongsTo" association like this:
javascript
Copy code
// Post model
const Post = sequelize.define('Post', {
    // post attributes
});

// User model
const User = sequelize.define('User', {
    // user attributes
});

// Define the association
Post.belongsTo(User);
This establishes a relationship where a Post belongs to a User.
hasOne Relationship:

Similar to "belongsTo," but the relationship is one-to-one, meaning one entity (e.g., a user) has only one associated entity (e.g., a profile).
For example, in a user profile scenario, a user can have only one profile.
In Sequelize, you can define a "hasOne" association like this:
javascript
Copy code
// User model
const User = sequelize.define('User', {
    // user attributes
});

// Profile model
const Profile = sequelize.define('Profile', {
    // profile attributes
});

// Define the association
User.hasOne(Profile);
This establishes a one-to-one relationship where a User has one associated Profile.
hasManyThrough Relationship:

This relationship involves traversing through multiple "hasMany" relationships to establish a connection.
For example, in an e-commerce application, a customer can have many orders, and each order can have many products.
In Sequelize, you can define a "hasManyThrough" association using the hasMany and belongsTo associations:
javascript
Copy code
// Customer model
const Customer = sequelize.define('Customer', {
    // customer attributes
});

// Order model
const Order = sequelize.define('Order', {
    // order attributes
});

// Product model
const Product = sequelize.define('Product', {
    // product attributes
});

