In this task candidates are asked to implement a REST service that can handle operations for amending account's balance.

For an on-site interview, it's recommended that an in-memory data-store is used, however, feel free to ask candidates to 
use any external data-store if they get to solve this challenge at home as they'll have more time. 

There are 3 difficulty levels in total where each subsequent level increases in complexity. A level consists of an API specification 
in the Open API 3.0 format and a Postman test suite. 

To complete a level, the corresponding Postman test suite must pass, however, for thorough assessment that might not be enough as it's depends a lot on what implementation the candidate opted for.      

Below you will find ideas for additional evaluation. 

### Level 0 
This is generally a warm-up exercise that tests general coding ability of a candidate. 

Here are the clues to search for:
 - Did they add any unit/API tests? What scenarios did they test (happy path, corner cases)?
 - Did they over-engineer their solution (this task requires minimum code)?

### Level 1
This level aims at testing candidate's understanding that in real life requests can be retried and that should be gracefully supported by the service.

Here are the clues to search for:
- Are they familiar with the idempotancy concept?
- Do they understand that it's the caller who must tell that a particular request is being retried (otherwise, it could just as well be 2 different requests with identical parameters)?
- Did they spot that they can use the `Transaction-Id` header for implementing idempotancy here? 
- Do they understand why it's a bad idea to pass such metadata as Transaction-ID in the request body?

### Level2
This level aims at testing candidates understanding of basic data structures and their ability to deal with changing requirements.

Here are the clues to search for:
- What data structure did they go for (Using hash-maps/dictionaries sounds reasonable here for quick fetching of a transaction/account balance)?
- What's the trade-off with using hash-maps/dictionaries (memory vs speed)?
- How does the `/balance` endpoint work now? Did they opt for maintaining the current account balance separate from the list of transactions (otherwise, the speed would grow lineary)?  
