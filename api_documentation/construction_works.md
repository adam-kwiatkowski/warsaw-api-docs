## API Documentation

This document provides information about the Warsaw City Construction Works API, which offers access to data related to construction works taking place on various streets within the city of Warsaw.

### Base URL

The base URL for accessing the API is:

```
https://api.um.warszawa.pl
```

### 1. Companies

This dataset allows you to retrieve a list of companies.

**Resource ID:** `2aa01577-9f24-4b8e-83f5-d3d15f6d094b`

**Supported Methods:** `GET`, `POST`

#### Request Parameters

- `resource_id` (required): The identifier of the resource.
- `apikey` (required): Your API key obtained after creating an account on `api.um.warszawa.pl`.

#### Response Elements

- `Value`: The name of the company.
- `Code`: The number assigned to the company.

#### Example Request

```bash
curl -X POST -H "Cache-Control: no-cache" \
"https://api.um.warszawa.pl/api/action/get_companies/?resource_id=2aa01577-9f24-4b8e-83f5-d3d15f6d094b&apikey=your_api_key"
```

### 2. Categories

This dataset allows you to retrieve a list of categories.

**Resource ID:** `e1c8fb95-9979-418d-bf5b-6bdfd586555b`

**Supported Methods:** `GET`, `POST`

#### Request Parameters

- `resource_id` (required): The identifier of the resource.
- `apikey` (required): Your API key obtained after creating an account on `api.um.warszawa.pl`.

#### Response Elements

- `ID`: The unique identifier of the category.
- `ParentID`: The reference to the parent category, if applicable.
- `Name`: The name of the category.
- `SpecialModeCode`: The type of the category.

#### Example Request

```bash
curl -X POST -H "Cache-Control: no-cache" \
"https://api.um.warszawa.pl/api/action/get_categories_tree/?resource_id=e1c8fb95-9979-418d-bf5b-6bdfd586555b&apikey=your_api_key"
```

### 3. Districts

This dataset allows you to retrieve a list of districts.

**Resource ID:** `f3469922-27e3-4d2f-811d-8efa2e448606`

**Supported Methods:** `GET`, `POST`

#### Request Parameters

- `resource_id` (required): The identifier of the resource.
- `apikey` (required): Your API key obtained after creating an account on `api.um.warszawa.pl`.

#### Response Elements

- `Value`: The name of the district.
- `Code`: The number assigned to the district.

#### Example Request

```bash
curl -X POST -H "Cache-Control: no-cache" \
"https://api.um.warszawa.pl/api/action/get_districts/?resource_id=f3469922-27e3-4d2f-811d-8efa2e448606&apikey=your_api_key"
```

### 4. Investments

This dataset allows you to retrieve a list of investments.

**Resource ID:** `26b9ade1-f5d4-439e-84b4-9af37ab7ebf1`

**Supported Methods:** `GET`, `POST`

#### Request Parameters

- `resource_id` (required): The identifier of the resource.
- `apikey` (required): Your API key obtained after

 creating an account on `api.um.warszawa.pl`.
- `pageSize`: The number of items per page (0 indicates all items).
- `StartIndex`: The current page number (starting from 0).
- `investName`: Narrow down the search to investments containing the specified name.
- `streetName`: Narrow down the search to investments located on the specified street.
- `companyCode`: Narrow down the search to investments associated with the specified company.
- `investNumber`: Narrow down the search to investments with the specified investment number.

#### Response Elements

- `ID`: The unique identifier for the investment.
- `Name`: The name of the investment.
- `Street`: The street where the construction work takes place.
- `StartDate`: The start date of the investment process.
- `EndDate`: The end date of the investment process.
- `LastModifyDate`: The last modification date of the investment object.

#### Example Request

```bash
curl -X POST -H "Cache-Control: no-cache" \
"https://api.um.warszawa.pl/api/action/get_open_invests/?resource_id=26b9ade1-f5d4-439e-84b4-9af37ab7ebf1&apikey=your_api_key&pageSize=10&StartIndex=15"
```

### 5. Investment Details

This dataset allows you to retrieve detailed information about an investment with a specific ID.

**Resource ID:** `25feb40c-f26a-428b-89ba-27ffefa795a5`

**Supported Methods:** `GET`, `POST`

#### Request Parameters

- `resource_id` (required): The identifier of the resource.
- `apikey` (required): Your API key obtained after creating an account on `api.um.warszawa.pl`.
- `investId` (required): The identifier of the investment.

#### Response Elements

- `ID`: The identifier of the investment.
- `InvestDesc`: The description of the investment.
- `InvestName`: The name of the investment.
- `CompanyName`: The name of the company.
- `CompanyID`: The unique identifier of the company.
- `Street`: The street where the investment is being carried out.
- `DistrictID`: The identifier of the district.
- `Form`: The starting street of the investment.
- `To`: The ending street of the investment.
- `CategoryId`: The unique identifier of the category.
- `InvestNumber`: The investment number.
- `StartDate`: The start date of the investment process.
- `EndDate`: The end date of the investment process.
- `CreationDate`: The date when the object was created.
- `StartWorkPlan`: The planned start date of the fieldwork.
- `EndWorkPlan`: The planned end date of the fieldwork.
- `StartWorkReal`: The actual start date of the fieldwork.
- `EndWorkReal`: The actual end date of the fieldwork.
- `CoordinationFinished`: Indicates if coordination is finished.
- `GuaranteeFrom`: The start date of the guarantee.
- `GuaranteeTo`: The end date of the guarantee.
- `GeoJson`: The geometry of the investment in GeoJson format.

#### Example Request

```bash
curl -X POST -H "Cache-Control: no-cache" \
"https://api.um.warszawa.pl/api/action/get_open_invest_details/?resource_id=25feb40c-f26a-428b-89ba-27ffefa795a5&apikey=your_api_key&investId=121263"
```