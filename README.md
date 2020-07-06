# SimpleDBCookieExample
A simple ASP.Net core app which sets a cookie from a GDPR style pop up, and talks to a MySQL database.  To test docker to docker working, which I am/was having trouble with.

There are two problems.  Firstly, how to connect to a MySQL database running inside a docker container.  This is straight-forward as it is just a connection string, assuming the container exports a port.  When this project is in a docker container, then you can use the IP address of the container, but this requires priviledges to be changed on the mysql user for the project.  Are we still using docker compose for this?  How can this be automated?

The second problem is one of cookies.  I have a pop up with a button - you click the button and it sets a cookie called .ASPNetCore.Consent or something to that effect.  I found, in a previous project, that if i ran this project on my desktop, then it worked fine, but if i ran the project inside a docker container, it was ignoring the new cookie.  This meant the pop up was ever present.

My own website runs on a cloud server, behind apache 2, which redirects to the docker container running the code.  Apache handles all the SSL stuff and the host name handling - the code knows nothing about this.  Will this fix the problem?  Is it a domain issue?  I don't know.

If you have answers, feel free to contact me.

I've put these two issues in the same project as they don't seem to cross each other too much - saves having two projects for such simple issues.
