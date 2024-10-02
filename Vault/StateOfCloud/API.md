Options:

Do everything with scan operations

-              How to do pagination? If every request is one query then we can simply paginate that using the lastevaluatedkey dynamo pagination.

-              Drawback: expensive compared to query operation

Query operations:

-              Cannot do sorting unless severity is the sort key (assuming we want to sort on severity, any other column would then be impossible)

-              Cannot do is_in in keycondition, i.e. we will have to do multiple queries to get all check_results for someone with multiple responsibilities in their scope (which many people will have). Then it’s very difficult to do pagination.

Ditch dynamo