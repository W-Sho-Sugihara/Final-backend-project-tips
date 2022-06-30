LS189 Interview Assessment Mock Questions

# From 175

- What is HTML?

- What is CSS?

- What is Sinatra?

- Is Sinatra a web server? If not what web server does it use?

- What is Rack?

- Rack's `rackup` file should end in what extention?

- What three values must be returned by the call method of a Rack application which describes the response sent to the client ?

- True or false:

  1, Routes are Ruby methods provided by Sinatra that typically use HTTP method names such as get, put, and delete.

  2, Routes use the method name and a pattern argument to determine the HTTP requests to which they respond.

  3, Routes use a block of code to determine the response sent back to the client.

  4, Routes must return a String that represents the body.

- Give three method names within Sinatra that define a route.

- Give an 2 example routes that would handle the path 'http://example.com/books/paperback/scifi?author=Andy+Weir'.

- What is an ERB layout?

- How is an ERB layout used within an ERB invocation?

- Within a Sinatra route, can the parameters within the params hash be extracted using either symbol keys or string keys?

- If you had content that needed to be loaded before processing each route, which method(s) would you use implement this behaviour?

- When are view helpers used in Sinatra?

- Which route can be used to process routes that are not explicitly defined within the application?

- How does Sinatra tell the browser to redirect to a new page?

- What kind of request does the browser make for the new page when handling a redirection.

- What three files do you need to run an application on Heroku?

- What is the purpose of a Procfile?

- What is the benefit of a multi-threaded web server?

- How do you enable sessions in Sinatra?

- What are resource-based routes and why are they useful?

- True or False: In terms of best practice, when a post request is executed, if the request is successful it redirects to a new route and if an error occurs then the current view is reloaded.

- Why is it a good idea to reload the current view rather than redirect after an error?

- Why are params cleared and all instance variables reset after a redirect?

- Why should we use view helpers?

- Why is it important to escape user input within a web application?

- What method can Sinatra use to escape html? (not the automatic html escape setting by the erubis gem `set :erb, :html_escape => true`)

- Your application has a form that the client uses to send a GET HTTP request. Where in the request will the form input values go?

- Which protocol should we use to send encrypted requests and responses between the client and the server?

- Are there any significant security differences between GET and POST requests?

- What is AJAX?

- What is XMLHttpRequest (XHR)?

- Within a Sinatra application, you want to display a particular kind of file to the client. Which Sinatra helper method can you use to do this?

- What is the Redcarpet gem's method `render` used for?

- From within a route, which method call accesses the application environment settings?

- List two ways to short-circuit a route in Sinatra.

- Why don’t we get the same hashed value back after hashing a specific password more than once?

- Why is it dangerous to allow raw filenames as request parameters?

# From 180

- What is a database?

- What is a RDBMS (relational database management system)?

# From 185

- What are some ways that we can optimize the way an application interacts with a database?

- What do we mean by an n + 1 query?

- What is a relation within a database?

- What is a relationship within a database?

- Define cardinality.

- Define modality.

- Identify the three sublanguages of SQL, provide examples.

- What is 'NULL' within SQL and how is it used and/or not used?

- Describe what primary, foreign, natural, and surrogate keys are.

- What are the three levels of Schema and describe each.

# Possible Project Question

- Why did you choose the project that you did?

- Explain the cardinality of your relationship(s).

- Explain the modality of those relationships.

- What were some difficulties you faced while designing your DB and app?

- What were some difficulties you faced while executing your design?

- What were some changes that you made allong the way? How did your project evolve?

- How did you impliment persistence within your app? (eg. user staying logged in)

- In what ways did you use sessions?

- What were some challenges you faced when querying data from the DB to be later displayed on your app?

- Did you use any custom classes (other than database_persistence)? What were their uses?

- What kind of values did your methods from '@storage' or from your database_persistence class return? single values, hashes, custom class obj's, arrays, etc? why did you choose the return value type that you did?

- Continued from previous question: If you could make changes would you change the return value format or keep your methods the same?

- How did you fulfill the requirement to return to the initial url if the current user wasnt logged and needed to log in first?

- Knowing what you know now, how would you have done your project differently?

- Knowing what you know now, what wouldn't you change about your app? What do you think you did well?

- Did you include user id's (or something similar) within the URL? why or why not?

- How was your experience with validation? Did you find it difficut or easy dealing with all the needed validations for form inputs and URL requests? why or why not?

- How was your experience with pagination? Was it difficult or easy? Why or why not? Would you do anything differently next time?

- Did you choose to use `limit` and `offset` within your query for pagination? Why or why not? How did it go?

- Did you have any difficulties deciding between when to reload current page vs when to redirect?

- Why did you choose path `/xxx/aa/yyyy/:bbb` for this GET route?

- Why did you choose path `/xxx/aa/yyyy/:bbb` for this POST route?

- Did you impliment encryption, AJAX or any other functionality not required within the project? How was your experience with them? Why did you choose to use them?

- Did you forget to add any gems to your gemfile upon submitting your project? Why do you think it can be easy to do so?

- Did you learn anything new while creating your app?

- Was there anything that you had previously learned that you now have a better understanding of because of the project?

- Was there anything you learned after submitting your project and received feedback?

- How was your experience using static assets? What did you use and why?

- Did you use tests during your project? why or why not?

- Were there any challenges while optimizing your database queries? What were they and how did you ovecome them?

- Did you use any dynamic views? (content changes depending on the route or variable) If so, how did you go about doing so?

- Was there a specific focus of your project? Something that you personally wanted to accomplish other than the project requirements?

- What part of the project was most frustrating or unenjoyable for you?

- What part of the project was the most fun for you?
