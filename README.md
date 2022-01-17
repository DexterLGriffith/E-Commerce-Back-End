# E-Commerce-Back-End

This is a back-end focused E-commerce website application that allows the user to interact with the SQL database, and manage the E-commerce site. 

## Description 

This back-end focused E-commerce applicaiton is a prebuilt application which uses express.js API to interact with sequelize and the MySQL database. Our job was to use the prebuilt application and make it to were the user can access their products, categories for their products, and the tags associated with the items. This application also allows the user to update, create, search for specific items, and delete data within the database. These actions are synced through the server using API post, put and delete routes within the Insomnia Core. 

## Tasks Completed

1. Created basic file from Github with readme.md, license and initial starting files. 
2. Created product.js model page, and category.js models page.
3. Created productTag.js and Tag.js model pages. 
4. Created Index.js models file to link all model pages. 
5. Created api routes, and finalized the "findAll" functions for each file [category, product and tag] to post in insomnia.

    Example: 

        Product.findAll({
            include: [{
            model: Category}, {model: Tag, through: ProductTag}
            ]
        })
6. Added findOne routes for all the different files. 

    Example: 

        Category.findOne({
            where: {id:req.params.id}, 
            include: [{
            model: Product,}
            ]
        })
7. Added the Create new routes for all different routes. 

    Example: 

        router.post('/', (req, res) => {
            Category.create(req.body)
            .then((result) => res.status(200).json(result))
            .catch(err =>{console.log(err)
            res.status(500).json(err)
            })
        });
8. Tested mysql application for proper functionality. 
9. Made sure all programs interact as they are intended to, and that there werent any major problems which caused the application to crash. 
10. After ensuring propfessional quality, it was uploaded to Github. 

## Installation 

1. Download files from the repository. 
2. Open Server.js and command terminal for the folder. 
3. Start MySQL server using command "mysql -u root -p".
4. Source db/schema.sql within MYSQL file. 
5. Open another command terminal within server.js and initialize npm.
6. After installing NPM, type in the command "npm run seed" to seed the files. 
7. After seeding the files, type in node server.js to initialize the server.
8. Open insomnia to specific file paths [example: "localhost:3001/api/products"]
9. Follow code within file and insomnia to POSAT, PUT and DELETE routes within the different files.  

## Links 

[Link to the Code Repository](https://github.com/DexterLGriffith/E-Commerce-Back-End)

[Screencastify](https://watch.screencastify.com/v/XeetlDxWjTudgjx7bsbR)


## Credits 

Dexter Griffith 

## References

1. https://smu.bootcampcontent.com/SMU-Coding-Bootcamp/smu-dal-fsf-pt-07-2021-u-c/-/blob/master/13-ORM/02-Homework/Assets/13-orm-homework-demo-01.gif
2. https://stackoverflow.com/questions/21260421/slow-mysql-query-to-get-product-id-and-its-category-id
3. https://smu.bootcampcontent.com/SMU-Coding-Bootcamp/smu-dal-fsf-pt-07-2021-u-c/-/blob/master/13-ORM/01-Activities/07-Ins_Update-Delete/routes/api/bookRoutes.js
4. https://smu.bootcampcontent.com/SMU-Coding-Bootcamp/smu-dal-fsf-pt-07-2021-u-c/-/tree/master/13-ORM/01-Activities/28-Stu_Mini-Project
5. https://www.tabnine.com/code/javascript/functions/sequelize/Model/findOne
6. https://sequelize.org/master/manual/model-querying-basics.html
