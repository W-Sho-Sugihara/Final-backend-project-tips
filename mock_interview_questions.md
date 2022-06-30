LS189 Interview Assessment Mock Questions

# From 175

- What is HTML?

  HTML helps us define the structure and flow of a web page. HTML sets the content of a web page. HTML is a markup language. A type of language that uses text to add certain distinct content elements to a page, such as lists, images, or tables. HTML is a language that contains hyperlinks, which we can use to navigate from one web page to another. (HTML stands for Hyper Text Markup Language)

- What is CSS?

  CSS is a language used to define the styles applied to a web page and stands for cascading style sheet.

- What is Sinatra?

  Sinatra is a Rack-based Ruby library that provides a framework that lets the developer create Ruby web applications. Sinatra is a productivity tool that helps web developers write the code necessary to manage and control a web application. Sinatra provides a DSL (put, get, before, etc.) that the web developer uses to write the web application.

- Is Sinatra a web server? If not what web server does it use?

  No, it is not a web server, but is a framework that provides the tools needed to create ruby web applications. Sinatra uses Webrick as its default web server.

- What is Rack?

  Rack is an interface between web servers and applications developed in Ruby. Rack provides the ability to wrap middleware and API's into a single method call handling HTTP requests and responses.

- Rack's `rackup` file should end in what extention?

  '.ru'

- What three values must be returned by the call method of a Rack application which describes the response sent to the client ?

  status code, request headers, the body

- True or false:

  1, Routes are Ruby methods provided by Sinatra that typically use HTTP method names such as get, put, and delete.

  (T)

  2, Routes use the method name and a pattern argument to determine the HTTP requests to which they respond.

  (T)

  3, Routes use a block of code to determine the response sent back to the client.

  (T)

  4, Routes must return a String that represents the body.

  (F)

- Give three examples of methods within Sinatra that define a route.

  get, post, delete, put, options, patch, link, unlink

- Give an 2 example routes that would handle the path 'http://example.com/books/paperback/scifi?author=Andy+Weir'.

  "/books/paperback/scifi", "/books/:type/scifi", "/books/:type/:genre", etc

- What is an ERB layout?

  ERB layout is a view template that wrap around other view templates

- How is an ERB layout used within an ERB invocation?

  `erb :index layout: :layout` or `erb :index`

- Within a Sinatra route, can the parameters within the params hash be extracted using either symbol keys or string keys?

  Yes, params[:user_id], params["user_id"] both work.

- If you had content that needed to be loaded before processing each route, which method(s) would you use implement this behaviour?

  `before`

- When are view helpers used in Sinatra?

  When a page is rendering. If during the rendering there is a specific piece of functionality required to complete the rendering that piece of functionality is stored as a view helper method. This helper method is then called later by the view template whenever that page is rendered.

- Which route can be used to process routes that are not explicitly defined within the application?

  `not_found do; ...; end`

- How does Sinatra tell the browser to redirect to a new page?

  It sends a Location response header with the desired location. It sets the response status code to a value that indicates redirection.

- What kind of request does the browser make for the new page when handling a redirection.

  `Get request`

- What three files do you need to run an application on Heroku?

  config.ru, Gemfile, Procfile

- What is the purpose of a Procfile?

  Heroku uses the Procfile to determine which processes to run when you use the application. Heroku uses the Procfile to determine the web server on which your application runs and the port number that your web server uses for your application.

- What is the benefit of a multi-threaded web server?

  A multi-threaded web server can handle simultaneous requests, with each request handled by a separate thread. This capability provides your production environment with the ability to handle requests that arrive simultaneously or in quick succession.

- How do you enable sessions in Sinatra?

  ```ruby
    configure do
      enable :sessions
      set :session_secret, "secret"
    end
  ```

- What are resource-based routes and why are they useful?

  The name of the data that a route displays or updates is part of the URL. It helps developers guess the URL that accomplishes a certain operation.

- True or False: In terms of best practice, when a post request is executed, if the request is successful it redirects to a new route and if an error occurs then the current view is reloaded.

  (true)

- Why is it a good idea to reload the current view rather than redirect after an error?

  Reloading a view maintains its access to the values within params and instance variables allowing for a form to keep its entered values, but redirecting clears params and resets all instance variables.

- Why are params cleared and all instance variables reset after a redirect?

  Because HTTP is a stateless protocol when we redirect, it is treated as a new request, therefore all params and instance variables from the previous request are lost.

- Why should we use view helpers?

  It removes logic from the view template and helps make your code more readable. It creates reusable code for multiple templates.

- Why is it important to escape user input within a web application?

  To prevent users from altering data within your application and to protect users from someone stealing their credentials

- What method can Sinatra use to escape html? (not the automatic html escape setting by the erubis gem `set :erb, :html_escape => true`)

  `Rack::Utils.escape_html(text)`

- Your application has a form that the client uses to send a GET HTTP request. Where in the request will the form input values go?

  In the request line as query parameters

- Which protocol should we use to send encrypted requests and responses between the client and the server?

  HTTPS

- Are there any significant security differences between GET and POST requests?

  No, they both send information in the form of plain text, just where the text is stored is different. GET stores information within the query parameters and POST stores them in the body. Security is more deteremined by wether if the request was encrypted or not, if user connections are password protected and if user inputs are escaped.

- What is AJAX?

  Stands for asynchonous JavaScript and XML. AJAX is a technique for creating dynamic web pages. AJAX allows for small portions of a web page to be reloaded without the entire page having to reload and without disrupting the display or functionality of the existing page.

- What is XMLHttpRequest (XHR)?

  "XMLHttpRequest is an API in the form of an object whose methods transfer data between a web browser and a web server. The object is provided by the browser's JavaScript environment." -Wikipedia

  "XMLHttpRequest (XHR) objects are used to interact with servers. You can retrieve data from a URL without having to do a full page refresh. This enables a Web page to update just part of a page without disrupting what the user is doing." -MDN Web Docs

- Within a Sinatra application, you want to display a particular kind of file to the client. Which Sinatra helper method can you use to do this?

  There should be a Content-Type header set in the response sent back to the client. To set the correct content type for the response, we can use the headers method (e.g. headers 'Content-Type' => 'text/plain'). This method returns a hash filled with key-value pairs, one pair for each header in the response.

- What is the Redcarpet gem's method `render` used for?

  To convert markdown into a HTML string.

- From within a route, which method call accesses the application environment settings?

  `env` & `request.env`

- List two ways to short-circuit a route in Sinatra.

  `redirect "new/path"` & `halt erb :new_view`

- Why don’t we get the same hashed value back after hashing a specific password more than once?

  Hashing a password uses a random salt value

- Why is it dangerous to allow raw filenames as request parameters?

  A malicious user can craft a filename that causes our application to reveal or alter sensitive information

# From 180

- What is a database?

  A structured collection of data stored on a computer.

- What is a RDBMS (relational database management system)?

  A software application that allows you to issue commands which let you interact with a relational database.

# From 185

- What are some ways that we can optimize the way an application interacts with a database?

  'Making the SQL queries that the application uses less general and more specialized. Pushing some aspects of the application logic (e.g. counting records) down to the database. Reducing the number of queries that an application needs to make. Analyzing and comparing the costs of running different SQL statements to identify which are the most efficient for the application to use.' -LS

- What do we mean by an n + 1 query?

  'Where an application issues one query to retrieve data for a parent record, and then an additional query for each child record associated with that parent.' -LS

- What is a relation within a database?

  A relation within a DB is a table/tuple.

- What is a relationship within a database?

  The association of data stored in multiple tables.

- Define cardinality.

  The relationship between the data in two different tables. Cardinality defines how many instances of an entity are related to instances of another entity.

- Define modality.

  The modality defines wether a relationship between entities is required or not.

- Identify the three sublanguages of SQL, provide examples.

  DDL: data definition language. (CREATE, DROP, ALTER)
  DML: data manipulation language. (INSERT, UPDATE, DELETE)
  DSL: data security language. (GRANT, INVOKE)

- What is 'NULL' within SQL and how is it used and/or not used?

  NULL represents the absence of a value or that a value is empty. `IS NULL` and `IS NOT NULL` operators must be used to determine wether a value is NULL or not. Values compared with NULL user any other camparison will return NULL.

- Describe what primary, foreign, natural, and surrogate keys are.

  PRIMARY KEY : a constraint which ensures that a column is both 'UNIQUE' and 'NOT NULL' hence uniquely identifying a row within a table. A table can only have one primary key.

  FOREIGN KEY : a constraint that allows a column to reference the primary key or other column of another table. A table can have multiple foreign keys referencing multiple tables. The foreign key constraint helps to maintain the referencial integrity of the data between the referencing and referenced tables.

  NATURAL KEY : uses values within a column or multiple columns to create a unique key to identify a row within a table. Natural keys use existing data and therefore the key has business meaning or in other words is relevent to the other columns within a table.

  SURROGATE KEY : is a system generated unique value that identifies a row in a table. A surrogate key has no business meaning and is therefore unrelated to all the other columns held in a table.

- What are the three levels of Schema and describe each.

  Conceptual Level : a high level design of a database typically only including the main entities of a database and the relationship among them. This design is database agnostic and highly abstract.

  Logical Level : A mid level design of a database including entities along with their attributes and the relations between the entities. This design is still database agnostic.

  Physical Level : A low level design of a database that includes tables, column info and the relationship between tables through foreign keys. A physical design is focused on implementation and is therefore specific to a database and is not agnostic.
