# SimpleAPI
The first step is to import the required packages: fmt, log, and net/http. fmt is used to print messages to the console, log is used to log any errors that occur during server operation, and net/http is used to build HTTP servers.

Two functions are defined: formHandler and helloHandler. These functions handle requests to the /form and /hello endpoints, respectively.

The formHandler function takes in two arguments: a ResponseWriter object and a Request object. The ResponseWriter object is used to write the response back to the client, and the Request object represents the incoming HTTP request.

The ParseForm() method of the Request object is called to parse the form data submitted in a POST request. If an error occurs during parsing, an error message is written to the ResponseWriter object.

If parsing is successful, the FormValue() method of the Request object is used to retrieve the values of the "name" and "address" form fields. These values are then printed to the ResponseWriter object.

The helloHandler function also takes in a ResponseWriter object and a Request object. It checks if the request path is "/hello" and if the HTTP method is GET. If both conditions are true, it writes "hello" to the ResponseWriter object.

In the main function, a file server is created using the http.FileServer() function. This server is set to handle requests for the root path ("/") and will serve any files in the "static" directory.

The http.HandleFunc() method is used to register the formHandler and helloHandler functions as handlers for the "/form" and "/hello" endpoints, respectively.

Finally, the server is started using the http.ListenAndServe() method, which listens for incoming HTTP requests on port 8000. If any errors occur during server operation, they are logged using the log.Fatal() method.
