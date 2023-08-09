# Currency Exchange Micro Service - H2

Run com.in28minutes.microservices.currencyconversionservice.CurrencyConversionServiceApplicationH2 as a Java Application.

## Resources

- http://localhost:8000/currency-exchange/from/USD/to/INR

```json
{
  "id": 10001,
  "from": "USD",
  "to": "INR",
  "conversionMultiple": 65.0,
  "environmentInfo": "NA"
}
```

## H2 Console

- http://localhost:8000/h2-console
- Use `jdbc:h2:mem:testdb` as JDBC URL

## Notes

## Tables Created

```
create table exchange_value
(
	id bigint not null,
	conversion_multiple decimal(19,2),
	currency_from varchar(255),
	currency_to varchar(255),
	primary key (id)
)
```
