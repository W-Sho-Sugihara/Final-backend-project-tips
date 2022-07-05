Hi,

At the time I took the RB189 project assessment there was no other information available other than the study guide so I would like to share with you some things I did that worked and things I learned or wish I had known before going into the project. I have broken up this document into two sections, the project itself and submiting the project.

** During the Project **

My first design concept was a library with books and users. Users would be able to checkout and return books from the library. Users would be able to view their currently checked out books and all books they had checked in the past. This quickly changed as viewing all books from the past was a many-to-many relationship within the DB and that was not recommended within the project. My design at this point however now didn't have enough CRUD within the app. I then added an admin attribute within my users to be able to add books to the library, update book information and delete books from the library. It was about at this point that I regretted my library concept. If I could do my project over I would pick a design which would allow more CRUD access to its users without having to deal with admins. For example, LS suggested an app that would track appartments and its tenants. The relationship between appartments and tenants is very clear and the current app user could easily be granted CRUD capabilities because the apt's and tenants belong to the current user. In my app however, the books belonged to the library and not the user, hence CRUD capabilities could not be granted to the user, but only to an admin (therefore more code).

What I learned from this was to spend a good amount of time during the design stage of your project and make sure that it meets the requirements of the project before moving forward. This being said however, I did not lose any points on my design. So if you wanted to make something similar, you can, as long as it meets the requirements and has all the functionality LS is looking for.

One trick that I learned that really helped me during my project was using bash scripts to delete, create and seed my DB with a single command. This really helped me when I was writing queries to insert, delete and update the DB. This simple bash script saved me a lot of time by resetting my DB after undesireable changes.

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

One thing that I struggled with was correctly choosing wether to reload or redirect. If you want to maintain the inputs within a form after an error you must reload the page, as redirect will reset all params and instance variables in the view. As a general rule, if a post request is successful then redirect, if an error occurs then reload page. This was a painful lesson for me as it can really negatively affect the UI of the app (which cost me some points as well).

Validations, validations, validations. Ouch they were painful. I lost a lot of points over incorrect or nonexisting validations. If you have the mindset of a hacker then you can skip this part, but for those of us who don't then I hope I can be of some help so people don't have to experience what I did. A validation lesson I leanred was don't try to bundle your validations into one or even just a couple conditionals. Break down your input validations one input at a time then combine those validation methods into one, two or however many methods you need to consolidate your code. Take your time and think of any and all possible edge cases.
Here is a small list of possible URL edge cases:

- user id, collection id, item id, page num is an invalid number
- user id, collection id, item id, page num is not a number but letters or other chars
- user id, collection id, item id, page num is 0
- not logged in
- logging out without being logged in
- admin?
- page doesn't exist

Here is small list of possible input edge cases:

- whitespace
- empty inputs
- incorrect boolean inputs (if using boolean, how are they evaluated?)
- future date inputs
- inputs longer than DB allows
- 0 or negative integers allowed?
- unique inputs? (user name, password, etc)
- password validation (eg. min 8 chas, alphanumeric, etc)
- re-enter password validations?

Something that a fellow student did that I wish I had was to organize my project into more files. He put all of his view helper methods into a separate file along as well as all his helper methods. Then `require_relative` on those files. This made it so that only the routes were in the main app file, view helpers and the helper methods in other files. This might not be your style if you prefer having all the app code in one file, but looking back I wish I had done this so I wouldn't have had to scroll back and forth through hundreds of lines of code.

** When Submitting **

When creating the README file for my project I tried to make navigating my project as easy as possible for someone who would be looking through hundreds of lines of code for the first time. I did this by creating a list of all the requirements and then writing where in my code the answers were found.

Example:

- some requirement.....

  On `line xx` this demonstrates an example of some requirement.

I was praised for this type of organization, so even though it probaby won't affect your score it will create a more pleasent experience for whomever will be grading your project (which in my mind is a plus).

Please remember to include the instruction to `bundle install`. If you forget to instruct whomever is grading your project to `bundle install` you will lose points.

Remember to include all the information needed to access your seed data like usernames and passwords. They will not look through your code to find this information and may ask you to fix it and resubmit.

Be sure to include all necessary gems within your `Gemfile`. You may be using a global gems within your project that isn't included within you Gemfile without realising it. I was using a yaml file within my project to seed data and forgot to include the `yaml` gem because it was installed globally and was called out on it.

Finally take the time to read all the instruction carefully regarding what is required in the README file, theres a lot of em ^^

** Final Thoughts **

This was a super fun project to do and I hope you have fun with it as well. As nervous as I was to submit my code, I was excited as well to be evaluated on what I was capable of right now. The grading of the project is rigorous and the deductions soul crushing at times, but remember that the TA's are rooting for you and not out to get you. The criticism I received was constructive and eye opening and really broadened my view and understanding of UI, validations and best practice. It was a very humbling experience, but at the same time confidence boosting where I did well.

Good Luck and happy coding ^^

Sho Sugihara
