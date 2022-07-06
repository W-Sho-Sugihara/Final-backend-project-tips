Hi,

At the time I took the RB189 project assessment there was no other information available other than the study guide so I would like to share with you some things I did that worked and things I learned or wish I had known before going into the project. I have broken up this document into two sections, the project itself and submiting the project.

** During the Project **

1, When I first designed my project I wrote it out all on paper, the relations, relationships, attributes of the DB, then the actual functionality of the app. I found this helpful to visualize the DB and the routes that would be needed within the app to create the desired functionality. Then I went to creating the schema and seed data for the DB. I was about half way finished with my routes when I reread the requirements and realized that I had missed some crucial functionality within my app. This required me to make adjustments, add attributes to my tables and add additional routes to compensate for my lack of functionality.

What I learned from this was to spend a good amount of time during the design stage of your project and make sure that it meets all the requirements of the project before moving forward. There are a lot of requirements and it is helpful to go through each one and conciously design your schema and project to meet each one before moving on to actual coding. If you do find your project lacking part way through don't worry, its not the end of the world. I was able to make the necessary adjustments in my design to give my app the functionality LS was lookign for so I'm sure you can too.

So thoroughly go through the requirements of the project before coding, during coding and when you think you are done. There are a lot of requirements for this project and none are taken lightly. Your project is thoroughly evaluated for every requirement listed so take your time to make sure you're not missing any requirements or edge cases.

2, One trick that I learned that really helped me during my project was using bash scripts to delete, create and seed my DB with a single command. This really helped me when I was writing queries to insert, delete and update the DB. This simple bash script saved me a lot of time by resetting my DB after undesireable changes.

```bash
bundle install

DATABASE=$1

dropdb $DATABASE
createdb $DATABASE

psql -d $DATABASE < schema.sql

ruby init.rb
```

For those not familiar with bash, the $1 points to the argument passed in when the script is called. So within the terminal (and from within your project folder) you would write:

`bash file_name.sh db_name`

The `db_name` should be the name of your database and `file_name.sh` should be your bash script file. The db_name is assigned to the variable `DATABASE` within the script and so the script will then delete db_name, then create a new DB, db_name and then populate the DB with whatever you have in your `schema.sql` file (make sure the file path is accessible). The script will then run the ruby file `init.rb` which is where I kept all of my seed data and the methods and queries needed to populate the DB. With this one bash script I was able drop, create and seed my DB wich was very very helpful.

3, One thing that I struggled with was correctly choosing whether to reload or redirect. If you want to maintain the inputs within a form after an error you must reload the page, as redirect will reset all params and instance variables in the view. As a general rule, if a post request is successful then redirect, if an error occurs then reload page. This was a painful lesson for me as it can really negatively affect the UI of the app.

4, Something that a fellow student did that I wish I had done was to organize my project into more files. He put all of his view helper methods into a separate file as well as all his helper methods. Then `require_relative` on those files. This made it so that only the routes were within the main app file, while the view helpers and the helper methods in other files. This might not be your style if you prefer having all the app code in one file, but looking back I wish I had done this so I wouldn't have had to scroll back and forth through hundreds of lines of code.

** When Submitting **

5, When creating the README file for my project I tried to make navigating my project as easy as possible for someone who would be looking through hundreds of lines of code for the first time. I did this by creating a list of all the requirements and then writing where in my code the answers were found.

Example:

- some requirement.....

  On `line xx` this demonstrates an example of some requirement.

I was praised for this type of organization, so even though it probaby won't affect your score, it will create a more pleasent experience for whomever will be grading your project (which in my mind is a plus).

Take the time to read all the instructions carefully regarding what is required in the README file, there's a lot of em ^^

** Final Thoughts **

This was a super fun project to do and I hope you have fun with it as well. As nervous as I was to submit my code, I was excited as well to be evaluated on what I was capable of right now. The grading of the project is rigorous and the deductions painful, but remember that the TA's are rooting for you and not out to get you. The criticism I received was constructive and eye opening and really broadened my view and understanding of UI, validations and best practice. It was a very humbling experience, but at the same time it boosted my confidence where I did well.

Good Luck and happy coding ^^

Sho Sugihara
