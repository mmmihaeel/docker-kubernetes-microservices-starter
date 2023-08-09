### Microservices

Docker, Kubernetes, CI, CD and build

### Currency Exchange Service

If you ask it the value of 1 USD in INR, or 1 Australian Dollar in INR, the Currency Exchange Service answers

- 1 USD is 60 INR
- 1 Australian Dollars is 50 INR.

http://localhost:8000/currency-exchange/from/EUR/to/INR

```json
{
  "id": 10002,
  "from": "EUR",
  "to": "INR",
  "conversionMultiple": 75.0,
  "exchangeEnvironmentInfo": "37f1ad927c6e v1 27c6e"
}
```

### Currency Conversion

Currency Conversion Service is used to convert a bucket of currencies. If you want to find the value of 10 USD, Currency Conversion Service returns 600.

- **STEP 1** : Currency Conversion Service calls the Currency Exchange Service for the value of 1 USD. It gets a response back saying 60.
- **STEP 2** : The Currency Conversion Service then multiplies 10 by 60, and returns 600 back.

http://localhost:8100/currency-conversion/from/EUR/to/INR/quantity/10

```json
{
  "id": 10002,
  "from": "EUR",
  "to": "INR",
  "conversionMultiple": 75.0,
  "quantity": 10,
  "totalCalculatedAmount": 750.0,
  "exchangeEnvironmentInfo": "37f1ad927c6e v1 27c6e",
  "conversionEnvironmentInfo": "fb6316b5713d v1 5713d"
}
```
