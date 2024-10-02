GenAI Taskforce is currently providing Azure accounts for OpenAI access. They are pushing back a bit at the moment because of the AWS first strategy.

Different user groups -> need to be identified. Non AWS-team cannot use bedrock, but they are interested in using it. Interest is growing.

Bedrock over OpenAI preference from PostNL. With good arguments it is ok to use OpenAI, like the performance of the Dutch language models

AI tools within platforms like Salesforce can be used without issue

Karin: Using an OpenAI model is often simply just an API call, not an entire workload.

Door open for innovation on other platforms/functionalities that are not on Azure/AWS. Like Cognigy.

JP: Yes room for innovation and trying things outside of these rules.

OpenAI is currently being used via Sogeti, who provide an API for teams to use.

Not a lot of development capabilities within the teams that want to use the models.

Karin: Different phases -> experimentation open for small teams and pocs, for going to production we need different standards to ensure security and reliability.

When teams want to run a workload in Azure, they request that to Sogeti with an application tag (that was assigned to them by Krijn) and Sogeti will tag their instance with this tag. So costs are allocated correctly.

Leone: what do teams want? Only inference or full access to the platform, e.g. to do fine tuning?
-> Looking at the competence of the team, probably (mostly) inference only and no model-building etc.

n8n is a good possibility for doing low-code quick and easy workflows that use GenAI. E.G. for analyzing simple files. There are also other services like this, AWS is building something. Could be useful for employees other that engineers as well

Karin: something a CoE can also start doing is simply start sharing useful sources, videos, solutions, best practices.

Private shared bedrock environment: there is a clear use case for this with Cognigy. This solution would be useful for that use case, but then the question arises, do we build it for this case only or do we immediately build a generic solution?

AI platform is used by data scientists to build their solutions on. But not fully mature yet. 


Cognigy was chosen for a genai platform? But when this tool was chosen there was a lot of focus on the functionals and not on the non-functionals. (Anne-Fleur van Kessel & Merel Donkers are working on Cognigy atm) So now we are figuring out that there are a lot of issues with privately connecting to Cognigy etc. Turns out they do not support mTLS and cannot connect to the private network. So a bit annoying, can we still go back?

Decision making: we need to come with concrete proposals and 

What use cases are bedrock and openAI for?
Communication with teams about AI CoE. Benefits need to outweigh the costs
Board needed for certain decisions (CCoE board?)
Who is going to use chatgpt and who will decide what people get licenses?
