The middleware in node.js is a function that will have all the access for requesting an object, responding to an object, and moving to the next middleware function in the application request-response cycle. 
syntax of middleware is:
             <pre>
             var requestTime = function (req, res, next)
             {
                 req.requestTime = Date.now()
                 next()
              }</pre>
<h1>What is next()?</h1>
Next() is a middleware function that calls for the control of another middleware once the code is completed. You can wait till the network operations are completed before you go to the next step. 
