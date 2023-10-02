---
description: List of possible actions in Task Designer UI
---

# Task Actions

Every Parameter of every Action can be set to either **Constant** value (by writing or copypasting something into parameter field) or to **Reference** value (by Drag\&Dropping **Action ID** field of the action we want to reference to **Parameter** field).

#### HTTP Request

Makes a HTTP Request to provided URL. You can choose method (GET/POST currently), add Body for post methods, add HTTP Headers.

* **Method** - POST or GET
* **URL** - _Single Value_. URL of your query.
* **Body** - _Single Value_. Body of your Post request.
* **Headers** - _Multi Value_. Set of headers for your request.

#### **JSON Value**

Gets tag value on selected Path from Body.

* **Body** - _Single Value_. JSON body that will be parsed.
* **Path** - _Single Value_. JSON Path in [JSON Pointer RFC 6901](https://datatracker.ietf.org/doc/html/rfc6901) notation (`/data/accounts/0`)

#### CBOR Value

Gets tag value on selected Path from Body.

* **Body** - _Single Value_. CBOR body that will be parsed.
* **Path** - _Single Value_. CBOR Path in [JSON Pointer RFC 6901](https://datatracker.ietf.org/doc/html/rfc6901) notation (`/data/accounts/0`)

#### TvmCell Encode

Encodes set of values into one TvmCell boc.

* **Values** - _Multi Value_. Math Actions results will be encoded as `uint256`. All other action results will be encoded as `string`.&#x20;

#### TvmCell Decode

Parses TvmCell boc and extracts given Abi Types from it. Gets selected Index from results.

* **CellBoC** - _Single Value_. TvmCell String (base64 encoded) that will be parsed.
* **ABI Type Names** - _Multi Value_. Specify all types in correct order that are encoded in BoC.
* **Index of Element** - _Single Value_. Index of array in **ABI Type Names** field that will be extracted as answer.

#### Multiply

Multiplies multiplicand and multiplicator.

* **Multiplicand** - _Single Value_. First value in multiplication.
* **Multiplicator** - _Single Value_. Second value in multiplication.

#### Divide

Divides divident with divisor.

* **Divident** - _Single Value_.  First value in divide.
* **Divisor** - _Single Value_. Can't be 0. Second value in divide.

#### Aggregate Functions (Average, Median, Max, Min, Sum)

Gets an array of Values, aggregates them with a function then rounds to a Precision.

* **Values** - _Multi Value_. Specify all values that should be aggregated.
* **Precision** - _Single Value_. Result will be rounded to this precision. Should be from -22 to 22.
