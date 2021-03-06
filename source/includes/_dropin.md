# Drop-in UI
The PokitDok Drop-in UI enables anyone to add functionality like eligibility checks or out-of-pocket cost estimation to their own website with a fully styled and functional UI.

* One simple drop-in with full customization
* All major insurance carriers
* Detailed eligibility info including deductible status and co-pays
* Out-of-pocket cost estimation based on location and eligibility information


## 1. Get Drop-in Token
First you will need to <a href='https://platform.pokitdok.com/signup' target='_blank'>sign up for a PokitDok Platform account</a>
and generate a `Drop-In Token` from the Platform dashboard <a href='https://platform.pokitdok.com/dashboard#/dropin' target='_blank'>Drop-In UI</a> page, where you will need
to provide the hostname of the website where you'll be using the drop-in UI, as well as select the type of drop-in UI widget you'll be using. For hostname,
provide the base URL of the site that you intend on embedding the widget (i.e.- `https://pokitdok.com` not `https://pokitdok.com/page/with/widget`).


## 2. Include JS File

```html
<script src="https://platform.pokitdok.com/sdk/dropin.min.js"></script>
```

Include the `dropin.min.js` file in your website.


## 3. Add HTML Container

```html
<div id="dropin-ui"></div>
```

Add an HTML container with a specific ID that will house your drop-in UI.


## 4. Initialize Drop-in

```javascript
pokitdok.dropin('INSERT YOUR DROP-IN TOKEN HERE', {
   container: 'dropin-ui'
   type: 'eligibility'
})
```

Call the `pokitdok.dropin` function, using your PokitDok Platform `Drop-In Token` and <a href='/#options'>options</a>.

The drop-in UI form will auto-populate in the HTML container that you specified.

## Types
There are two types of drop-in UIs to choose from:

### Eligibility

> Eligibility example with minimum required options:

```javascript
pokitdok.dropin('INSERT YOUR DROP-IN TOKEN HERE', {
    container: 'dropin-ui',
    type: 'eligibility'
}
```

Displays a form that requires first & last name, birth date, insurance provider, and member id.
Returns eligibility information in an easy to read format with detailed info including deductible status and co-pays.

### Calculator

<aside class="warning">
an array of 'procedures' is required for the drop-in UI calculator to work.
</aside>

> Calculator example with minimum required options:

```javascript
pokitdok.dropin('INSERT YOUR DROP-IN TOKEN HERE', {
    container: 'dropin-ui',
    type: 'calculator',
    procedures: [
        {
            'name': 'Test Procedure',
            'cpt_code': 'xxxxx'
        }
    ]
}
```

Displays a form that requires all the same fields as the eligibility type, with an added required procedure field and geolocation functionality
for closest possible price estimation. Returns an out of pocket cost estimation based on average insurance prices and location information for the procedure that was selected, as well as
eligibility. Displays in an easy to read format with detailed info including deductible status and co-pays.

#### Calculator Specific Options:

Name                    | Type                    | Default  | Description
------------------------|-------------------------|----------|--------------------------------------------------------------------------------------
procedures              | Array                   | Null     | Procedure(s) to populate the procedure dropdown with; `name` and `cpt_code` are required
procedures.name         | String                  | Null     | The name of the procedure that will show in the form dropdown
procedures.cpt_code     | String/Array (cpt code) | Null     | Either an array of associated CPT Codes or a string of a single CPT Code for the procedure
values.procedure        | String/Array (cpt code) | Null     | The procedure that will be auto-selected once the form loads
showPriceRange          | Boolean                 | False    | Show insurance price and out-of-pocket estimate results as a range of prices rather than an average
showCalculatorMessages  | Boolean                 | False    | Show a message below the out-of-pocket results explaining how calculation was made
eligibilityResultsFirst | Boolean                 | False    | On results page, show eligibility results first and out-of-pocket results below that

## Options

> Example with options:

```javascript
pokitdok.dropin('INSERT YOUR DROP-IN TOKEN HERE', {
    container: 'dropin-ui',
    type: 'eligibility',
    styles: 'http://www.example.com/styles.css',
    values: {
        'trading_partner_id': 'MOCKPAYER'
    },
    pieChartColors: {
        'fill': '#000000',
        'background': '#333333'
    },
    autoSubmit: true,
    resetButton: true,
    onFormSuccess: function() {
        // do stuff here
    },
    onFormLoad: function() {
        // do stuff here
    }
}
```

> Example of all fields pre-populated using `values` option:

```json

{
    "zip_code": "94401",
    "member": {
        "first_name": "Jane",
        "last_name": "Doe",
        "id": "123456789",
        "birth_date": "1970-01-01"
    },
    "trading_partner_id": "MOCKPAYER",
    "procedure": "xxxxx",
    "provider": {
        "first_name": "JEROME",
        "last_name": "AYA-AY",
        "npi": "1467560003"
    }
}
```

<aside class="warning">
'container' and 'type' are required options for the drop-in UI to work.<BR>
'procedures' is required for the calculator type drop-in.
</aside>

Name                      | Type                | Default  | Description
--------------------------|---------------------|----------|--------------------------------------------------------------------------------------
container                 | String              | Null     | The id of the HTML container that the drop-in UI will be housed in
type                      | String              | Null     | Set the desired functionality of the drop-in; either `eligibility` or `calculator`
styles                    | String (url)        | Null     | URL pointing to a css file to overwrite styles
pieChartColors            | Object              | Null     | Change the colors of the pie chart in the eligibility results
pieChartColors.fill       | String (hex color)  | Null     | Color of the filled-in section of the pie chart on the eligibility results
pieChartColors.background | String (hex color)  | Null     | Color of the background section of the pie chart on the eligibility results
values                    | Object              | Null     | An object of values that the form will pre-populate with
values.provider           | Object              | Null     | NPI to use for eligibility checks
autoSubmit                | Boolean             | False    | Form should submit automatically once all fields are filled
resetButton               | Boolean             | False    | A button should show that allows form to be reset once submitted
onFormSuccess             | Function            | Null     | Call when the form has been submitted successfully
onFormLoad                | Function            | Null     | Call when the form has been loaded successfully
