# lenskit-dashboard

Setup:
1. install node.js - https://nodejs.org/en/
2. Run the following on command line:  
     npm install https://github.com/mapbox/node-sqlite3/tarball/master  
     npm install --save express@4.15.2  
     npm install --save socket.io  
     npm install body-parser  

To Run:
1. Run on command line: node server
2. Will be listening at localhost:3000

Functionality:
* 'Current Experiments' button opens a dropdown that displays numbered experiments currently stored in the database. This button will refresh its contents every time it is pressed, as well as any time the table/browser state changes.
* 'Refresh' will script refresh the page, updating the state of all jobs (or subjobs) in view, as well as updating the dropdown contents.
* 'Return to Jobs' is visible when viewing subjobs. It will return to the list containing the parent jobs of that experiment.
* Clicking on a table row when viewing jobs in an experiment will show you the list of its subjobs.
* Clicking on a table row when viewing subjobs will act the same as the 'Return to Jobs' button.
* Clicking on a table column header will sort it in descending/ascending order.
* Using the browser refresh button will act the same as the 'Refresh Button'.
* Using the browser back/forward buttons will return you the the previous/next page state and will update the table.
* If you need to know the ID of an experiment, read the id following 'cE=' in the address bar.
* If you need to know the ID of a job, click on the job to view its subjobs and read the id following 'cJ=' in the address bar.

Table Layout:
* ID is a simpler generated number to keep track of jobs.
* Status displays 'waiting/tt-setup/tt-train/tt-test/completed' depending on current subjob state.
* Start/Finish displays the time the job started to the time it finished (or 'Running' if unfinished).
* Progress displays an indeterminate progress bar if in 'waiting/tt-setup/tt-train' state, determinate with CompletedSteps/TotalSteps if in 'tt-test' state, and the total job run time if in the 'completed' state.
