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
the code i have writen for this was
<!-- 
const express = require ('express')
const app = express();
const middleware1 = (req,res,next) =>{
    console.log("middleware 1")
    next()
}
const middleware2 = (req,res,next) =>{
    console.log("middleware 2 for globally")
    next()
}
app.use(middleware2);

app.get('/link1', middleware1,(req,res)=>{
    res.send("<h1>Link1 with middleware 1 and 2</h1>")
})

app.get('/link2', middleware1,(req,res)=>{
    res.send("<h1>Link2 with middleware 1 and 2</h1>")
})

app.get('/link3',(req,res)=>{
    res.send("<h1>Link2 with middleware 1 and 2</h1>")
})
app.listen(5000, () =>{
    console.log("server started")
}) -->

in this i have used two middlewave and 1middlewave is applicable for only two express routes
and the next will be used for the express routes
for   ---> app.use(middleware2);
the app.use  is used when we want to use the middilewave for all the routes

