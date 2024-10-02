Tool that does checks on cdk code to check for compliance and security. Idea is that it will find issues before deployment. To do this it uses a rule set (devsecops (?)) that should be the same dataset as we use in OCDS (how do we ensure that?)). However, teams can also suppress findings in CDK nag. That means that they can deploy the code even though there is a CDK nag rule that would normally block it. If teams implement a suppression, they don't want to see a finding come up for the same issue in the SoC dataset. That is why we want to get the CDK nag suppressions from the teams so that we can also suppress these in the SoC dataset. 

Idea is now that we provide an API endpoint where suppressions are posted so that we integrate them into our SoC dataset. We need to know what data will be sent (full report on all findings? Only suppressions? They mentioned a contract), when it is sent (only on deployment or at synth time as well?) and how we want it (directly in s3 or - our preference -  just as the body of an api call), as well as how we want to handle it on the ocds side (just as part of normal check-result-statuses?). The latter we should discuss with Sjuul before the next meeting. -> Yes normal check-result-statuses

Check result status -> how long do they want to suppress it? Default length or add a date in NAG.

NAG number + arn, we need a mapping of the NAG number and the checks

suppression -> we as postnl don't want postnl to look at this
status update -> we as team don't want to do it



- Exactly what data will be transferred? (contract?)
	- Report that is sent contains -> RuleId, ResourceId, compliance, ExceptionReason, ruleLevel, ruleInfo, resourceIdHash (sha256 of resourceId), versionNumber
	- if suppressed: compliance = Suppressed, exceptionReason = user supplied reason, date
	- compliance can also be 'leveled down', instead of error can become a warning. compliance will then be 'Non-Compliant' and ruleLevel will be warning.
	- there will be urls in the settings as well that link to confluence reports.
- How do we want to transfer it? (API body/S3?)
	- API or SSM automated document?
- When will it be sent? (every time someone deploys?)
	- They have two options, either only on github deploys or on local deploys as well
- From where will it be sent?
	- Either lambda or github runner.
- What does the CDK nag ruleset look like?
		- No ARN, but hash of the resource path -> tags on the actual resource 
- How long should something be suppressed? Default date or add a date in NAG.
	- They can add a date.
- How do they get the rules from devsecops?
	- Devsecops rules are from an Excel doc made by security, some rules in there are clear and strict, others are more open to interpretation. Rolf & Pete used this document to create a specific cdk nag ruleset that is used in nag. We will need to make sure that we have a single source of truth for this. Probably easiest if we in OCDS pull the nag ruleset from the DKS guys.


Report per app?