## Benefits Enrollment

*Available modes of operation: batch/async only*

> Example enrollment request to enroll a subscriber in benefits. (Health, Dental, Vision)

```shell
curl -i -H "Authorization: Bearer $ACCESS_TOKEN" -H "Content-Type: application/json" -XPOST -d '{
    "action": "Change",
    "dependents": [],
    "master_policy_number": "ABCD012354",
    "payer": {
        "tax_id": "654456654"
    },
    "purpose": "Original",
    "sponsor": {
        "tax_id": "999888777"
    },
    "subscriber": {
        "address": {
            "city": "CAMP HILL",
            "county": "CUMBERLAND",
            "line": "100 MARKET ST",
            "line2": "APT 3G",
            "postal_code": "17011",
            "state": "PA"
        },
        "benefit_status": "Active",
        "benefits": [
            {
                "begin_date": "2015-01-25",
                "benefit_type": "Health",
                "coordination_of_benefits": [
                    {
                        "group_or_policy_number": "890111",
                        "payer_responsibility": "Primary",
                        "status": "Unknown"
                    }
                ],
                "late_enrollment": false,
                "maintenance_type": "Addition"
            },
            {
                "begin_date": "2015-01-25",
                "benefit_type": "Dental",
                "late_enrollment": false,
                "maintenance_type": "Addition"
            },
            {
                "begin_date": "2015-01-25",
                "benefit_type": "Vision",
                "late_enrollment": false,
                "maintenance_type": "Addition"
            }
        ],
        "birth_date": "1940-01-25",
        "contacts": [
            {
                "communication_number2": "7172341240",
                "communication_type2": "Work Phone Number",
                "primary_communication_number": "7172343334",
                "primary_communication_type": "Home Phone Number"
            }
        ],
        "eligibility_begin_date": "2014-01-25",
        "employment_status": "Full-time",
        "first_name": "JOHN",
        "gender": "Male",
        "group_or_policy_number": "123456001",
        "handicapped": false,
        "last_name": "DOE",
        "maintenance_reason": "Active",
        "maintenance_type": "Addition",
        "member_id": "123456789",
        "middle_name": "P",
        "relationship": "Self",
        "ssn": "123456789",
        "subscriber_number": "123456789",
        "substance_abuse": false,
        "tobacco_use": false
    },
    "trading_partner_id": "MOCKPAYER"
}' https://platform.pokitdok.com/api/v4/enrollment/
```

```python
client.enrollment({
    "action": "Change",
    "dependents": [],
    "master_policy_number": "ABCD012354",
    "payer": {
        "tax_id": "654456654"
    },
    "purpose": "Original",
    "sponsor": {
        "tax_id": "999888777"
    },
    "subscriber": {
        "address": {
            "city": "CAMP HILL",
            "county": "CUMBERLAND",
            "line": "100 MARKET ST",
            "line2": "APT 3G",
            "postal_code": "17011",
            "state": "PA"
        },
        "benefit_status": "Active",
        "benefits": [
            {
                "begin_date": "2015-01-25",
                "benefit_type": "Health",
                "coordination_of_benefits": [
                    {
                        "group_or_policy_number": "890111",
                        "payer_responsibility": "Primary",
                        "status": "Unknown"
                    }
                ],
                "late_enrollment": False,
                "maintenance_type": "Addition"
            },
            {
                "begin_date": "2015-01-25",
                "benefit_type": "Dental",
                "late_enrollment": False,
                "maintenance_type": "Addition"
            },
            {
                "begin_date": "2015-01-25",
                "benefit_type": "Vision",
                "late_enrollment": False,
                "maintenance_type": "Addition"
            }
        ],
        "birth_date": "1940-01-25",
        "contacts": [
            {
                "communication_number2": "7172341240",
                "communication_type2": "Work Phone Number",
                "primary_communication_number": "7172343334",
                "primary_communication_type": "Home Phone Number"
            }
        ],
        "eligibility_begin_date": "2014-01-25",
        "employment_status": "Full-time",
        "first_name": "JOHN",
        "gender": "Male",
        "group_or_policy_number": "123456001",
        "handicapped": False,
        "last_name": "DOE",
        "maintenance_reason": "Active",
        "maintenance_type": "Addition",
        "member_id": "123456789",
        "middle_name": "P",
        "relationship": "Self",
        "ssn": "123456789",
        "subscriber_number": "123456789",
        "substance_abuse": False,
        "tobacco_use": False
    },
    "trading_partner_id": "MOCKPAYER",
})
```

```csharp
 client.enrollment(
        new Dictionary<string, object> {
        { "action", "Change"},
         {"dependents", new List<string> { } },
         {"master_policy_number", "ABCD012354"},
         { "payer", new Dictionary<string, object> {
                { "tax_id", "654456654" }
             }
         },
         {   "purpose", "Original"},
         {   "sponsor", new Dictionary<string, object> {
                {"tax_id", "999888777" }
         } },
        { "subscriber", new Dictionary<string, object> {
                { "address", new Dictionary<string, object> {
                { "city", "CAMP HILL"},
                { "county", "CUMBERLAND"},
                { "line", "100 MARKET ST"},
                { "line2", "APT 3G"},
                { "postal_code", "17011"},
                { "state", "PA" }
                }},
                { "benefit_status", "Active"},
                { "benefits", new List<Dictionary<string, object>> {
                                new Dictionary<string, object> {
                                    { "begin_date", "2015-01-25"},
                                    { "benefit_type", "Health"},
                                    { "coordination_of_benefits", new List<Dictionary<string, object>> {
                                        new Dictionary<string, object> {
                                                { "group_or_policy_number", "890111"},
                                                { "payer_responsibility", "Primary"},
                                                { "status", "Unknown" }
                                            }
                                        }
                                    },
                                    { "late_enrollment", false},
                                    { "maintenance_type", "Addition" }
                                }, // benefits[0]
                                new Dictionary<string, object> {
                                    { "begin_date", "2015-01-25"},
                                    { "benefit_type", "Dental"},
                                    { "late_enrollment", false},
                                    { "maintenance_type", "Addition" }
                                    },
                                new Dictionary<string, object> {
                                    { "begin_date", "2015-01-25"},
                                    { "benefit_type", "Vision"},
                                    { "late_enrollment", false},
                                    { "maintenance_type", "Addition" }
                                    }} // End list
                    },
                    { "birth_date", "1940-01-25"},
                    { "contacts", new List<Dictionary<string, object>> {
                            new Dictionary<string, object> {
                                { "communication_number2", "7172341240"},
                                { "communication_type2", "Work Phone Number"},
                                { "primary_communication_number", "7172343334"},
                                { "primary_communication_type", "Home Phone Number" }
                                }
                    } },
                    { "eligibility_begin_date", "2014-01-25"},
                    { "employment_status", "Full-time"},
                    { "first_name", "JOHN"},
                    { "gender", "Male"},
                    { "group_or_policy_number", "123456001"},
                    { "handicapped", false},
                    { "last_name", "DOE"},
                    { "maintenance_reason", "Active"},
                    { "maintenance_type", "Addition"},
                    { "member_id", "123456789"},
                    { "middle_name", "P"},
                    { "relationship", "Self"},
                    { "ssn", "123456789"},
                    { "subscriber_number", "123456789"},
                    { "substance_abuse", false},
                    { "tobacco_use", false
                }} },
                { "trading_partner_id", "MOCKPAYER" }
        });
```

```ruby
client.enrollment({
    action: "Change",
    dependents: [],
    master_policy_number: "ABCD012354",
    payer: {
        tax_id: "654456654"
    },
    purpose: "Original",
    sponsor: {
        tax_id: "999888777"
    },
    subscriber: {
        address: {
            city: "CAMP HILL",
            county: "CUMBERLAND",
            line: "100 MARKET ST",
            line2: "APT 3G",
            postal_code: "17011",
            state: "PA"
        },
        benefit_status: "Active",
        benefits: [
            {
                begin_date: "2015-01-25",
                benefit_type: "Health",
                coordination_of_benefits: [
                    {
                        group_or_policy_number: "890111",
                        payer_responsibility: "Primary",
                        status: "Unknown"
                    }
                ],
                late_enrollment: false,
                maintenance_type: "Addition"
            },
            {
                begin_date: "2015-01-25",
                benefit_type: "Dental",
                late_enrollment: false,
                maintenance_type: "Addition"
            },
            {
                begin_date: "2015-01-25",
                benefit_type: "Vision",
                late_enrollment: false,
                maintenance_type: "Addition"
            }
        ],
        birth_date: "1940-01-25",
        contacts: [
            {
                communication_number2: "7172341240",
                communication_type2: "Work Phone Number",
                primary_communication_number: "7172343334",
                primary_communication_type: "Home Phone Number"
            }
        ],
        eligibility_begin_date: "2014-01-25",
        employment_status: "Full-time",
        first_name: "JOHN",
        gender: "Male",
        group_or_policy_number: "123456001",
        handicapped: false,
        last_name: "DOE",
        maintenance_reason: "Active",
        maintenance_type: "Addition",
        member_id: "123456789",
        middle_name: "P",
        relationship: "Self",
        ssn: "123456789",
        subscriber_number: "123456789",
        substance_abuse: false,
        tobacco_use: false
    },
    trading_partner_id: "MOCKPAYER",
})
```

```java
StringBuffer buf = new StringBuffer();

buf.append("{");
buf.append("    \"action\": \"Change\",");
buf.append("    \"dependents\": [],");
buf.append("    \"master_policy_number\": \"ABCD012354\",");
buf.append("    \"payer\": {");
buf.append("        \"tax_id\": \"654456654\"");
buf.append("    },");
buf.append("    \"purpose\": \"Original\",");
buf.append("    \"sponsor\": {");
buf.append("        \"tax_id\": \"999888777\"");
buf.append("    },");
buf.append("    \"subscriber\": {");
buf.append("        \"address\": {");
buf.append("            \"city\": \"CAMP HILL\",");
buf.append("            \"county\": \"CUMBERLAND\",");
buf.append("            \"line\": \"100 MARKET ST\",");
buf.append("            \"line2\": \"APT 3G\",");
buf.append("            \"postal_code\": \"17011\",");
buf.append("            \"state\": \"PA\"");
buf.append("        },");
buf.append("        \"benefit_status\": \"Active\",");
buf.append("        \"benefits\": [");
buf.append("            {");
buf.append("                \"begin_date\": \"2015-01-25\",");
buf.append("                \"benefit_type\": \"Health\",");
buf.append("                \"coordination_of_benefits\": [");
buf.append("                    {");
buf.append("                        \"group_or_policy_number\": \"890111\",");
buf.append("                        \"payer_responsibility\": \"Primary\",");
buf.append("                        \"status\": \"Unknown\"");
buf.append("                    }");
buf.append("                ],");
buf.append("                \"late_enrollment\": false,");
buf.append("                \"maintenance_type\": \"Addition\"");
buf.append("            },");
buf.append("            {");
buf.append("                \"begin_date\": \"2015-01-25\",");
buf.append("                \"benefit_type\": \"Dental\",");
buf.append("                \"late_enrollment\": false,");
buf.append("                \"maintenance_type\": \"Addition\"");
buf.append("            },");
buf.append("            {");
buf.append("                \"begin_date\": \"2015-01-25\",");
buf.append("                \"benefit_type\": \"Vision\",");
buf.append("                \"late_enrollment\": false,");
buf.append("                \"maintenance_type\": \"Addition\"");
buf.append("            }");
buf.append("        ],");
buf.append("        \"birth_date\": \"1940-01-25\",");
buf.append("        \"contacts\": [");
buf.append("            {");
buf.append("                \"communication_number2\": \"7172341240\",");
buf.append("                \"communication_type2\": \"Work Phone Number\",");
buf.append("                \"primary_communication_number\": \"7172343334\",");
buf.append("                \"primary_communication_type\": \"Home Phone Number\"");
buf.append("            }");
buf.append("        ],");
buf.append("        \"eligibility_begin_date\": \"2014-01-25\",");
buf.append("        \"employment_status\": \"Full-time\",");
buf.append("        \"first_name\": \"JOHN\",");
buf.append("        \"gender\": \"Male\",");
buf.append("        \"group_or_policy_number\": \"123456001\",");
buf.append("        \"handicapped\": false,");
buf.append("        \"last_name\": \"DOE\",");
buf.append("        \"maintenance_reason\": \"Active\",");
buf.append("        \"maintenance_type\": \"Addition\",");
buf.append("        \"member_id\": \"123456789\",");
buf.append("        \"middle_name\": \"P\",");
buf.append("        \"relationship\": \"Self\",");
buf.append("        \"ssn\": \"123456789\",");
buf.append("        \"subscriber_number\": \"123456789\",");
buf.append("        \"substance_abuse\": false,");
buf.append("        \"tobacco_use\": false");
buf.append("    },");
buf.append("    \"trading_partner_id\": \"MOCKPAYER\"");
buf.append("}");

JSONObject query = (JSONObject) JSONValue.parse(buf.toString());
Map<String, Object> results = client.enrollment(query);
```

>Example change request to add a dependent due to a qualifying life event. (Health)

```shell
{
    "action": "Change",
    "dependents": [
        {
            "benefit_status": "Active",
            "benefits": [
                {
                    "begin_date": "2014-01-25",
                    "benefit_type": "Health",
                    "late_enrollment": false,
                    "maintenance_type": "Addition"
                }
            ],
            "birth_date": "1999-01-25",
            "education_end_date": "2016-01-25",
            "first_name": "JAMES",
            "gender": "Male",
            "group_or_policy_number": "123456001",
            "handicapped": false,
            "last_name": "DOE",
            "maintenance_reason": "Initial Enrollment",
            "maintenance_type": "Addition",
            "middle_name": "E",
            "relationship": "Child",
            "school": {
                "organization_name": "PENN STATE UNIVERSITY"
            },
            "ssn": "987654321",
            "student_status": "Full-time",
            "subscriber_number": "123456789",
            "substance_abuse": false,
            "tobacco_use": false
        }
    ],
    "master_policy_number": "ABCD012354",
    "payer": {
        "tax_id": "654456654"
    },
    "purpose": "Original",
    "sponsor": {
        "tax_id": "999888777"
    },
    "subscriber": {
        "contacts": [],
        "handicapped": false,
        "member_id": "987654321",
        "substance_abuse": false,
        "tobacco_use": false
    },
    "trading_partner_id": "MOCKPAYER"
}
```

```python
client.enrollment({
    "action": "Change",
    "dependents": [
        {
            "benefit_status": "Active",
            "benefits": [
                {
                    "begin_date": "2014-01-25",
                    "benefit_type": "Health",
                    "late_enrollment": False,
                    "maintenance_type": "Addition"
                }
            ],
            "birth_date": "1999-01-25",
            "education_end_date": "2016-01-25",
            "first_name": "JAMES",
            "gender": "Male",
            "group_or_policy_number": "123456001",
            "handicapped": False,
            "last_name": "DOE",
            "maintenance_reason": "Initial Enrollment",
            "maintenance_type": "Addition",
            "middle_name": "E",
            "relationship": "Child",
            "school": {
                "organization_name": "PENN STATE UNIVERSITY"
            },
            "ssn": "987654321",
            "student_status": "Full-time",
            "subscriber_number": "123456789",
            "substance_abuse": False,
            "tobacco_use": False
        }
    ],
    "master_policy_number": "ABCD012354",
    "payer": {
        "tax_id": "654456654"
    },
    "purpose": "Original",
    "sponsor": {
        "tax_id": "999888777"
    },
    "subscriber": {
        "contacts": [],
        "handicapped": False,
        "member_id": "987654321",
        "substance_abuse": False,
        "tobacco_use": False
    },
    "trading_partner_id": "MOCKPAYER",
})
```

```csharp
client.enrollment(
    new Dictionary<string, object> {
        {"action", "Change"},
        {"dependents", new Object[] {new Dictionary<string, object> {
                    {"benefit_status", "Active"},
                    {"benefits", new Object[] {new Dictionary<string, object> {
                                {"begin_date", "2014-01-25"},
                                {"benefit_type", "Health"},
                                {"late_enrollment", false},
                                {"maintenance_type", "Addition"}
                            }}},
                    {"birth_date", "1999-01-25"},
                    {"education_end_date", "2016-01-25"},
                    {"first_name", "JAMES"},
                    {"gender", "Male"},
                    {"group_or_policy_number", "123456001"},
                    {"handicapped", false},
                    {"last_name", "DOE"},
                    {"maintenance_reason", "Initial Enrollment"},
                    {"maintenance_type", "Addition"},
                    {"middle_name", "E"},
                    {"relationship", "Child"},
                    {"school", new Dictionary<string, string> {
                            {"organization_name", "PENN STATE UNIVERSITY"}
                        }},
                    {"ssn", "987654321"},
                    {"student_status", "Full-time"},
                    {"subscriber_number", "123456789"},
                    {"substance_abuse", false},
                    {"tobacco_use", false}
                }}},
        {"master_policy_number", "ABCD012354"},
        {"payer", new Dictionary<string, string> {
                {"tax_id", "654456654"}
            }},
        {"purpose", "Original"},
        {"sponsor", new Dictionary<string, string> {
                {"tax_id", "999888777"}
            }},
        {"subscriber", new Dictionary<string, object> {
                {"contacts", new string[] {}},
                {"handicapped", false},
                {"member_id", "987654321"},
                {"substance_abuse", false},
                {"tobacco_use", false}
            }},
        {"trading_partner_id", "MOCKPAYER"}
    });
```

```ruby
client.enrollment({
    action: "Change",
    dependents: [
        {
            benefit_status: "Active",
            benefits: [
                {
                    begin_date: "2014-01-25",
                    benefit_type: "Health",
                    late_enrollment: false,
                    maintenance_type: "Addition"
                }
            ],
            birth_date: "1999-01-25",
            education_end_date: "2016-01-25",
            first_name: "JAMES",
            gender: "Male",
            group_or_policy_number: "123456001",
            handicapped: false,
            last_name: "DOE",
            maintenance_reason: "Initial Enrollment",
            maintenance_type: "Addition",
            middle_name: "E",
            relationship: "Child",
            school: {
                organization_name: "PENN STATE UNIVERSITY"
            },
            ssn: "987654321",
            student_status: "Full-time",
            subscriber_number: "123456789",
            substance_abuse: false,
            tobacco_use: false
        }
    ],
    master_policy_number: "ABCD012354",
    payer: {
        tax_id: "654456654"
    },
    purpose: "Original",
    sponsor: {
        tax_id: "999888777"
    },
    subscriber: {
        contacts: [],
        handicapped: false,
        member_id: "987654321",
        substance_abuse: false,
        tobacco_use: false
    },
    trading_partner_id: "MOCKPAYER",
})
```

```java
StringBuffer buf = new StringBuffer();

buf.append("{");
buf.append("    \"action\": \"Change\",");
buf.append("    \"dependents\": [");
buf.append("        {");
buf.append("            \"benefit_status\": \"Active\",");
buf.append("            \"benefits\": [");
buf.append("                {");
buf.append("                    \"begin_date\": \"2014-01-25\",");
buf.append("                    \"benefit_type\": \"Health\",");
buf.append("                    \"late_enrollment\": false,");
buf.append("                    \"maintenance_type\": \"Addition\"");
buf.append("                }");
buf.append("            ],");
buf.append("            \"birth_date\": \"1999-01-25\",");
buf.append("            \"education_end_date\": \"2016-01-25\",");
buf.append("            \"first_name\": \"JAMES\",");
buf.append("            \"gender\": \"Male\",");
buf.append("            \"group_or_policy_number\": \"123456001\",");
buf.append("            \"handicapped\": false,");
buf.append("            \"last_name\": \"DOE\",");
buf.append("            \"maintenance_reason\": \"Initial Enrollment\",");
buf.append("            \"maintenance_type\": \"Addition\",");
buf.append("            \"middle_name\": \"E\",");
buf.append("            \"relationship\": \"Child\",");
buf.append("            \"school\": {");
buf.append("                \"organization_name\": \"PENN STATE UNIVERSITY\"");
buf.append("            },");
buf.append("            \"ssn\": \"987654321\",");
buf.append("            \"student_status\": \"Full-time\",");
buf.append("            \"subscriber_number\": \"123456789\",");
buf.append("            \"substance_abuse\": false,");
buf.append("            \"tobacco_use\": false");
buf.append("        }");
buf.append("    ],");
buf.append("    \"master_policy_number\": \"ABCD012354\",");
buf.append("    \"payer\": {");
buf.append("        \"tax_id\": \"654456654\"");
buf.append("    },");
buf.append("    \"purpose\": \"Original\",");
buf.append("    \"sponsor\": {");
buf.append("        \"tax_id\": \"999888777\"");
buf.append("    },");
buf.append("    \"subscriber\": {");
buf.append("        \"contacts\": [],");
buf.append("        \"handicapped\": false,");
buf.append("        \"member_id\": \"987654321\",");
buf.append("        \"substance_abuse\": false,");
buf.append("        \"tobacco_use\": false");
buf.append("    },");
buf.append("    \"trading_partner_id\": \"MOCKPAYER\"");
buf.append("}");

JSONObject query = (JSONObject) JSONValue.parse(buf.toString());
Map<String, Object> results = client.enrollment(query);
```

> Example request to terminate a subscriber's benefits.

```shell
{
    "action": "Change",
    "dependents": [],
    "payer": {
        "tax_id": "654456654"
    },
    "purpose": "Original",
    "sponsor": {
        "tax_id": "999888777"
    },
    "subscriber": {
        "benefit_status": "Active",
        "contacts": [],
        "eligibility_end_date": "2015-01-25",
        "employment_status": "Terminated",
        "first_name": "JOHN",
        "group_or_policy_number": "123456001",
        "handicapped": false,
        "last_name": "DOE",
        "maintenance_reason": "Termination of Employment",
        "maintenance_type": "Cancellation or Termination",
        "member_id": "123456789",
        "middle_name": "E",
        "relationship": "Self",
        "ssn": "123456788",
        "subscriber_number": "123456789",
        "substance_abuse": false,
        "tobacco_use": false
    },
    "trading_partner_id": "MOCKPAYER"
}
```

```python
client.enrollment({
    "action": "Change",
    "dependents": [],
    "payer": {
        "tax_id": "654456654"
    },
    "purpose": "Original",
    "sponsor": {
        "tax_id": "999888777"
    },
    "subscriber": {
        "benefit_status": "Active",
        "contacts": [],
        "eligibility_end_date": "2015-01-25",
        "employment_status": "Terminated",
        "first_name": "JOHN",
        "group_or_policy_number": "123456001",
        "handicapped": False,
        "last_name": "DOE",
        "maintenance_reason": "Termination of Employment",
        "maintenance_type": "Cancellation or Termination",
        "member_id": "123456789",
        "middle_name": "E",
        "relationship": "Self",
        "ssn": "123456788",
        "subscriber_number": "123456789",
        "substance_abuse": False,
        "tobacco_use": False
    },
    "trading_partner_id": "MOCKPAYER",
})
```

```csharp
client.enrollment(
    new Dictionary<string, object> {
        {"action", "Change"},
        {"dependents", new string[] {}},
        {"payer", new Dictionary<string, string> {
                {"tax_id", "654456654"}
            }},
        {"purpose", "Original"},
        {"sponsor", new Dictionary<string, string> {
                {"tax_id", "999888777"}
            }},
        {"subscriber", new Dictionary<string, object> {
                {"benefit_status", "Active"},
                {"contacts", new string[] {}},
                {"eligibility_end_date", "2015-01-25"},
                {"employment_status", "Terminated"},
                {"first_name", "JOHN"},
                {"group_or_policy_number", "123456001"},
                {"handicapped", false},
                {"last_name", "DOE"},
                {"maintenance_reason", "Termination of Employment"},
                {"maintenance_type", "Cancellation or Termination"},
                {"member_id", "123456789"},
                {"middle_name", "E"},
                {"relationship", "Self"},
                {"ssn", "123456788"},
                {"subscriber_number", "123456789"},
                {"substance_abuse", false},
                {"tobacco_use", false}
            }},
        {"trading_partner_id", "MOCKPAYER"}
    }
);
```

```ruby
client.enrollment({
    action: "Change",
    dependents: [],
    payer: {
        tax_id: "654456654"
    },
    purpose: "Original",
    sponsor: {
        tax_id: "999888777"
    },
    subscriber: {
        benefit_status: "Active",
        contacts: [],
        eligibility_end_date: "2015-01-25",
        employment_status: "Terminated",
        first_name: "JOHN",
        group_or_policy_number: "123456001",
        handicapped: false,
        last_name: "DOE",
        maintenance_reason: "Termination of Employment",
        maintenance_type: "Cancellation or Termination",
        member_id: "123456789",
        middle_name: "E",
        relationship: "Self",
        ssn: "123456788",
        subscriber_number: "123456789",
        substance_abuse: false,
        tobacco_use: false
    },
    trading_partner_id: "MOCKPAYER",
})
```

```java
StringBuffer buf = new StringBuffer();

buf.append("{");
buf.append("    \"action\": \"Change\",");
buf.append("    \"dependents\": [],");
buf.append("    \"payer\": {");
buf.append("        \"tax_id\": \"654456654\"");
buf.append("    },");
buf.append("    \"purpose\": \"Original\",");
buf.append("    \"sponsor\": {");
buf.append("        \"tax_id\": \"999888777\"");
buf.append("    },");
buf.append("    \"subscriber\": {");
buf.append("        \"benefit_status\": \"Active\",");
buf.append("        \"contacts\": [],");
buf.append("        \"eligibility_end_date\": \"2015-01-25\",");
buf.append("        \"employment_status\": \"Terminated\",");
buf.append("        \"first_name\": \"JOHN\",");
buf.append("        \"group_or_policy_number\": \"123456001\",");
buf.append("        \"handicapped\": false,");
buf.append("        \"last_name\": \"DOE\",");
buf.append("        \"maintenance_reason\": \"Termination of Employment\",");
buf.append("        \"maintenance_type\": \"Cancellation or Termination\",");
buf.append("        \"member_id\": \"123456789\",");
buf.append("        \"middle_name\": \"E\",");
buf.append("        \"relationship\": \"Self\",");
buf.append("        \"ssn\": \"123456788\",");
buf.append("        \"subscriber_number\": \"123456789\",");
buf.append("        \"substance_abuse\": false,");
buf.append("        \"tobacco_use\": false");
buf.append("    },");
buf.append("    \"trading_partner_id\": \"MOCKPAYER\"");
buf.append("}");

JSONObject query = (JSONObject) JSONValue.parse(buf.toString());
Map<String, Object> results = client.enrollment(query);
```

Following the X12 834 format, the Benefits Enrollment API eases the creation and transmission process
of benefits enrollment and maintenance files. Applications can use the Enrollment
endpoint to submit new enrollments, enrollment changes due to life events and
plan termination. These files are submitted asynchronously via batch mode. In addition, the Enrollment
endpoint has the ability to accept an individual enrollment request. At this time, the number of trading 
partners with the ability to accept individual enrollment files is limited. For more information on individual 
request please [contact us](/contact).

File transmission is performed depending on carrier and group requirements. The
Benefits Enrollment API can be utilized for all enrollment requirements
including open enrollment and is able to support both full and change files.

PokitDok only transmits 834 files and responses to and from carriers. We do
not perform scrubbing or editing of submissions, or provide front-end interfaces
to manage benefits. File transmission is subject to carrier and group
requirements. Since enrollment requirements vary greatly between carriers,
please [contact us](/contact) to get started integrating benefits enrollment
and maintenance into your solution.

Learn more about our [Benefits Enrollment API
workflow](https://platform.pokitdok.com/benefit-enrollment).

Available Enrollment Endpoints:

| Endpoint     | HTTP Method | Description                                                           |
|:-------------|:------------|:----------------------------------------------------------------------|
| /enrollment/ | POST        | Submit a benefits enrollment request to the specified trading partner |

These are some of the most commonly used parameters accepted by the enrollment
endpoint. For a complete reference to all possible values in an enrollment
request, see our [benefits enrollment reference](benefits_enrollment.html).
<a name="enrollment_table"></a>

| Parameter                                  | Description                                                                                                                                             |
|:-------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------|
| dependents                                 | A list of dependents covered under benefits by the subscriber.                                                                                          |
|                                            | Each dependent list item may utilize the same request parameters as a subscriber.                                                                       |
| master_policy_number                       | The master policy number for the sponsor.                                                                                                               |
| sponsor                                    | The employer/sponsor of the benefits.                                                                                                                   |
| sponsor.name                               | The name of the sponsor.                                                                                                                                |
| sponsor.tax_id                             | The tax id of the sponsor.                                                                                                                              |
| subscriber                                 | The subscriber/employee of the benefits.                                                                                                                |
| subscriber_number                          | The subscribers identification number.                                                                                                                  |
| subscriber.address                         | The address for the subscriber.                                                                                                                         |
| subscriber.address.city                    | The city for the subscriber.                                                                                                                            |
| subscriber.address.county                  | The county for the subscriber.                                                                                                                          |
| subscriber.address.line                    | The first address line for the subscriber.                                                                                                              |
| subscriber.address.line2                   | The second address line for the subscriber.                                                                                                             |
| subscriber.address.postal_code             | The postal/zip code for the subscriber.                                                                                                                 |
| subscriber.benefits                        | The list of benefits for the subscriber.                                                                                                                |
| subscriber.benefits.begin_date             | The date benefits start for this list item. In ISO8601 format (YYYY-MM-DD).                                                                             |
| subscriber.benefits.benefit_type           | The type of benefit.                                                                                                                                    |
| subscriber.benefits.end_date               | The date benefits end for this list item. In ISO8601 format (YYYY-MM-DD).                                                                               |
| subscriber.benefits.late_enrollment        | Is the benefit enrolling late? True or False.                                                                                                           |
| subscriber.benefits.maintenance_resason    | The reason for benefit maintenance.<br/>Acceptable values: see <a href="#maintenance_reason_codes">reasons</a>                                          |
| subscriber.benefits.maintenance_type       | The type of benefit maintenance.<br/>Acceptable values: see <a href="#maintenance_type_codes">types</a>                                                 |
| subscriber.birth_date                      | The date of birth for the subscriber. In ISO8601 format (YYYY-MM-DD).                                                                                   |
| subscriber.eligibility_begin_date          | The date benefits become eligible for the subscriber. In ISO8601 format (YYYY-MM-DD).                                                                   |
| subscriber.eligibility_end_date            | The date benefits become ineligible for the subscriber. In ISO8601 format (YYYY-MM-DD).                                                                 |
| subscriber.employment_status               | The employment status for the subscriber.<br/>Acceptable values: see <a href="#employment_status_codes">statuses</a>                                    |
| subscriber.first_name                      | The first name for the subscriber.                                                                                                                      |
| subscriber.gender                          | The gender for the subscriber.<br/>Acceptable values: see <a href="#gender_codes">gender codes</a>                                                      |
| subscriber.benefits.group_or_policy_number | The group or policy number for this list item.                                                                                                          |
| subscriber.handicapped                     | Is the subscriber handicapped? True or False.                                                                                                           |
| subscriber.last_name                       | The last name for the subscriber.                                                                                                                       |
| subscriber.late_enrollment                 | Is the subscriber a late enrollee? True or False.                                                                                                       |
| subscriber.member_id                       | The member id for the subscriber if already enrolled in benefits.                                                                                       |
| subscriber.middle_name                     | The middle name for the subscriber.                                                                                                                     |
| subscriber.primary_communication_number    | The primary communication number for the subscriber.                                                                                                    |
| subscriber.primary_communication_type      | The type of primary communication above.<br/>Acceptable values: see <a href="#communication_type_codes">communication types</a>                         |
| subscriber.secondary_communication_number  | The secondary communication number for the subscriber.                                                                                                  |
| subscriber.secondary_communication_type    | The type of secondary communication above. <br/>Acceptable values: see <a href="#communication_type_codes">communication types</a>                      |
| subscriber.ssn                             | The social security number for the subscriber.                                                                                                          |
| subscriber.substance_abuse                 | Does the subscriber have a problem with substance abuse? True or False.                                                                                 |
| subscriber.suffix                          | The suffix for the subscriber.                                                                                                                          |
| subscriber.tobacco_use                     | Does the subscriber use tobacco? True or False.                                                                                                         |
| subscriber.relationship                    | The relationship of the subject of the transaction to the policy holder.<br/>Acceptable values: see <a href="#api_relationships">relationship codes</a> |                                                                              
| trading_partner_id                         | Unique id for the intended trading partner, as specified by the Trading Partners endpoint.                                                              |
*Additional parameters can be submitted to the carrier depending on the needs of specific groups or carriers.*

Responses to enrollment submissions can vary greatly from carrier to carrier. PokitDok will work with the carrier trading partner to provide confirmation of successful delivery and communicate any reports back to the client.

### Validation Codes

The following are the acceptable values for various parameters in the table above.

<a name="api_relationships"></a>

| Relationship Codes (<a href="#enrollment_table">back</a>) |                              |
|:----------------------------------------------------------|:-----------------------------|
| spouse                                                    | father                       |
| mother                                                    | grandfather                  |
| grandmother                                               | grandson                     |
| granddaughter                                             | aunt                         |
| uncle                                                     | nephew                       |
| niece                                                     | cousin                       |
| adopted_child                                             | foster_child                 |
| son_in_law                                                | daughter_in_law              |
| brother_in_law                                            | sister_in_law                |
| mother_in_law                                             | father_in_law                |
| brother                                                   | sister                       |
| ward                                                      | step_parent                  |
| step_son                                                  | step_daughter                |
| self                                                      | child                        |
| sponsored_dependent                                       | dependent_of_minor_dependent |
| ex_spouse                                                 | guardian                     |
| court_appointed_guardian                                  | collateral_dependent         |
| life_partner                                              | annuitant                    |
| trustee                                                   | other_relationship           |
| other_relative                                            |                              |


<a name="gender_codes"></a>

| Gender Codes (<a href="#enrollment_table">back</a>) |
|:----------------------------------------------------|
| Female                                              |
| Male                                                |
| Unknown                                             |

<a name="maintenance_type_codes"></a>

| Maintenance Type Codes (<a href="#enrollment_table">back</a>) |                                     |
|:--------------------------------------------------------------|:------------------------------------|
| Change                                                        | Delete                              |
| Addition                                                      | Cancellation or Termination         |
| Reinstatement                                                 | Correction                          |
| Audit or Compare                                              | Employee Information Not Applicable |

<a name="maintenance_reason_codes"></a>

| Maintenance Reason Codes (<a href="#enrollment_table">back</a>) |                                                                      |
|:----------------------------------------------------------------|:---------------------------------------------------------------------|
| Divorce                                                         | Birth                                                                |
| Death                                                           | Retirement                                                           |
| Adoption                                                        | Strike                                                               |
| Termination of Benefits                                         | Termination of Employment                                            |
| Consolidation Omnibus Budget Reconciliation Act (COBRA)         | Consolidation Omnibus Budget Reconciliation Act (COBRA) Premium Paid |
| Surviving Spouse                                                | Voluntary Withdrawal                                                 |
| Primary Care Provider (PCP) Change                              | Quit                                                                 |
| Fired                                                           | Suspended                                                            |
| Active                                                          | Disability                                                           |
| Plan Change                                                     | Change in Identifying Data Elements                                  |
| Declined Coverage                                               | Pre-Enrollment                                                       |
| Initial Enrollment                                              | Benefit Selection                                                    |
| Legal Separation                                                | Marriage                                                             |
| Personnel Data                                                  | Leave of Absence with Benefits                                       |
| Leave of Absence without Benefits                               | Lay Off with Benefits                                                |
| Lay Off without Benefits                                        | Re-enrollment                                                        |
| Change of Location                                              | Non Payment                                                          |

<a name="benefit_status_codes"></a>

| Benefit Status Codes |                                                        |
|:---------------------|:-------------------------------------------------------|
| Active               | Consolidated Omnibus Budget Reconciliation Act (COBRA) |
| Surviving Insured    | Tax Equity and Fiscal Responsibility Act (TEFRA)       |

<a name="employment_status_codes"></a>

| Employment Status Codes |                            |
|:------------------------|:---------------------------|
| Active                  | Active Military - Overseas |
| Active Military - USA   | Full-time                  |
| Leave of Absence        | Part-time                  |
| Retired                 | Terminated                 |

<a name="communication_type_codes"></a>

| Communication Type Codes (<a href="#enrollment_table">back</a>) |                     |
|:----------------------------------------------------------------|:--------------------|
| Electronic Mail                                                 | Telephone Extension |
| Facsimile                                                       | Telephone           |
| Home Phone Number                                               | Work Phone Number   |
| Cellular Phone                                                  | Beeper Number       |
| Alternate Telephone                                             |                     |
