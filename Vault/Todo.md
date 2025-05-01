
Went wells of onboarding:
Checklist worked really well
Easy pipeline story to learn about the system (This time with rapid7 it was a bit too much)

Keer zitten met Michelle
Onderwerp voor Q3
Ontwikkelpunten op papier zetten

Suppressed filter dynamo







Thinking fast and slow
team topology
management myth


Install wsl on windows (with ubuntu)
on ubuntu install node (https://nodejs.org/en/download/package-manager -> on linux using nvm)
C drive mounted at /mnt/c/
Install python
install node modules (npm install)
install python venv (see evo .setup/evo_local_setup.sh)
install git in wsl + authenticate
Show wsl terminal in vscode


```
{
    "version": "0",
    "id": "d3cf15ac-372b-9192-e4f9-39aad0de79b5",
    "detail-type": "LPE AVM Workload Create Completed",
    "source": "lpe.avm",
    "account": "767015857616",
    "time": "2024-11-05T17:12:45Z",
    "region": "eu-west-1",
    "resources": [],
    "detail": {
        "accounts": [
            {
                "stage": "dev",
                "stage_type": "non-prod",
                "account_name": "account-name-d",
                "account_id": "577638364313",
                "email_address": "aws-p+0512@postnl.nl"
            },
                        {
                "stage": "prd",
                "stage_type": "prod",
                "account_name": "account-name-d",
                "account_id": "577638364314",
                "email_address": "aws-p+0513@postnl.nl"
            },
                        {
                "stage": "deploy",
                "stage_type": "non-prod",
                "account_name": "account-name-d",
                "account_id": "577638364315",
                "email_address": "aws-p+0514@postnl.nl"
            }
        ],
        "organization_tier": "prd",
        "change_number": "W2411 624",
        "application_name": "STAP",
        "aws_workload_type": "cns",
        "caller_email": "john.d@postnl.nl",
        "caller_name": "Caspers, Merijn",
        "account_type": "sandbox",
        "cns_account": false,
        "csp_account": false,
        "grid": "G00867",
        "cost_code": "BHR10068-1-3",
        "contact_name": "John D",
        "contact_email": "john.d@postnl.nl",
        "contact_telephone": "31653243844",
        "request_date": "2024-11-05 16:39:43",
        "change_id": "5fae5f39-1569-4b79-929c-91c94854438b",
        "process_request_type": "avm",
        "is_subprocess": true,
        "cloud_service_provider": "CCoE",
        "developers": [
            ""
        ],
        "team_name": "johnd",
        "eventName": "CreateWorkloadCompleted"
    }
}
```



reference_date timestamp
source_reference_date timestamp
asset_check_first_date date
asset_check_last_updated timestamp
check_inactive_date date
rejectable boolean
policy_start_date date
internal_severity_date date
action_inserted_timestamp timestamp
action_date date



check_suppressed_in_source
suppressed