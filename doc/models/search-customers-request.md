## Search Customers Request

Defines the fields included in the request body for the
SearchCustomers endpoint.

### Structure

`SearchCustomersRequest`

### Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cursor` | `string` | Optional | Include the pagination cursor in subsequent calls to this endpoint to retrieve<br>the next set of results associated with the original query.<br><br>See the [Pagination guide](https://developer.squareup.com/docs/working-with-apis/pagination) for more information. |
| `limit` | `long|int` | Optional | A limit on the number of results to be returned in a single page.<br>The limit is advisory - the implementation may return more or fewer results.<br>If the supplied limit is negative, zero, or is higher than the maximum limit<br>of 1,000, it will be ignored. |
| `query` | [`Customer Query`](/doc/models/customer-query.md) | Optional | Represents a query (filtering and sorting criteria) used to search<br>for customer profiles. |

### Example (as JSON)

```json
{
  "query": {
    "filter": {
      "creation_source": {
        "values": [
          "THIRD_PARTY"
        ],
        "rule": "INCLUDE"
      },
      "created_at": {
        "start_at": "2018-01-01T00:00:00-00:00",
        "end_at": "2018-02-01T00:00:00-00:00"
      }
    },
    "sort": {
      "field": "CREATED_AT",
      "order": "ASC"
    }
  },
  "limit": 2
}
```

