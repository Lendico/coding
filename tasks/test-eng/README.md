# Test Engineer
Binaries provided deploys a service to port 8080.  

## RESTful service URLs
`POST /generate-plan`  
with json body :-
```
{
	"loanAmount": "5000",
	"nominalRate": "5.0",
	"duration": 24,
	"startDate": "2018-01-01"
}
```
Example Output:
```
[
    {
        "borrowerPaymentAmount": 219.36,
        "date": "2018-01-01T00:00:00Z",
        "initialOutstandingPrincipal": 5000,
        "interest": 20.83,
        "principal": 198.53,
        "remainingOutstandingPrincipal": 4801.47
    },
    {
        "borrowerPaymentAmount": 219.36,
        "date": "2018-02-01T00:00:00Z",
        "initialOutstandingPrincipal": 4801.47,
        "interest": 20.01,
        "principal": 199.35,
        "remainingOutstandingPrincipal": 4602.12
    },
    ...
    {
        "borrowerPaymentAmount": 219.28,
        "date": "2019-12-01T00:00:00Z",
        "initialOutstandingPrincipal": 218.37,
        "interest": 0.91,
        "principal": 218.37,
        "remainingOutstandingPrincipal": 0
    }
]
```  

`POST /calc-annuity`  
with json body :-
```
{
	"loanAmount": "5000",
	"nominalRate": "5.0",
	"duration": 24
}
```
Example Output:
```
{
    "annuity": "219.36"
}
```