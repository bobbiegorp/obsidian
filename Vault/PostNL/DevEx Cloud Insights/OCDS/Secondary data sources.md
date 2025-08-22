Athena create table statement is just like any other athena query. I.e. if you run it in boto3, there is a startqueryexecution api call that starts an execution and returns whether the query was successfully started. However if the query fails you cannot see that in the response. You need to do separate api calls to get the query execution status and that may take a while. So the question is: do we wait for the table creation to finish to see if it was successful or not?

TODO: 
create bucket for secondary sources, with right permissions for QS and ?? -> discuss how many buckets