# API

Unofficial Church of Jesus Christ API Documentation

## Sample Data

This dummy data is used throughout the documentation.

| ID         | Name                                     | Type       |
| ---------: | ---------------------------------------- | :--------- |
| 1000000001 | Harry James Potter (M)<br>31 Jul, 1980   | Individual |
| 1000000002 | Ginevra Molly Potter (F)<br>11 Aug, 1981 | Individual |
|    2000001 | Hogwarts School Stake                    | Stake      |
|     300001 | Gryffindor House Ward                    | Ward       |

## Member Card

```txt
GET /services/member-card?id=1000000001&includeAddhouseholdDatas=true&lang=eng&type=INDIVIDUAL
Host: lcr.churchofjesuschrist.org
```

Query Options:

- `&includeAddhouseholdDatas=true`
- `&includePriesthood=true`

```json
{
  "id": "1000000001",
  "name": "Harry Potter",
  "nameOrder": null,
  "listName": "Potter, Harry",
  "spokenName": "Harry Potter",
  "label": "Harry Potter",
  "mrn": null,
  "displayMrn": null,
  "phone": "801-555-4444",
  "individualPhone": "801-555-4444",
  "email": "harry.potter@example.com",
  "age": 40,
  "ageAsOfDec31": 41,
  "ageAsOfDec31NextYear": null,
  "actualAge": 40,
  "actualAgeInMonths": 487,
  "priesthood": null,
  "priesthoodType": null,
  "allPriesthoodOrdinations": null,
  "nextRecommendedPriesthoodType": null,
  "pendingPriesthoodType": null,
  "pendingWardInterviewDate": null,
  "pendingBishopApproves": null,
  "priesthoodCode": null,
  "melchizedek": null,
  "birthDate": "31 Jul 1980",
  "birthDateCmis": "19803107",
  "baptismDateCmis": null,
  "baptismEligibleDateCmis": null,
  "deaconEligibleDateCmis": null,
  "teacherEligibleDateCmis": null,
  "priestEligibleDateCmis": null,
  "elderEligibleDateCmis": null,
  "highPriestEligibleDateCmis": null,
  "confirmationDateCmis": null,
  "info": null,
  "info2": null,
  "gender": "MALE",
  "name1": "Potter, Harry James",
  "name2": null,
  "legalName": "Harry James Potter",
  "position": null,
  "address1": null,
  "address2": null,
  "address3": null,
  "address4": null,
  "unitNumber": 300001,
  "unitName": "Gryffindor House Ward",
  "unitAbbreviation": "3",
  "unitType": "WARD",
  "parentUnitNumber": 2000001,
  "parentUnitName": "Hogwarts School Stake",
  "parentUnitType": "STAKE",
  "adultAgeOrMarried": true,
  "oouMember": false,
  "linkedRecord": false,
  "residesInWardOrBranch": true,
  "headOfHousehold": true,
  "youngMissionary": false,
  "missionary": false,
  "endowed": false,
  "defaultClassAssignmentTypeIds": null,
  "currentClassAssignmentSubOrgNames": null,
  "recommendWarning": null,
  "recommendError": null,
  "recommendStatus": null,
  "priesthoodRestrictionMessage": null,
  "priesthoodRestrictionMessageDetails": null,
  "restrictMelPriesthood": false,
  "rbr": false,
  "value": null
}
```

## Household Image

```txt
GET /services/photos/manage-photos/approved-image-household/1000000001?lang=eng&addable=false
Host lcr.churchofjesuschrist.org
```

```json
{
  "name": "Potter, Harry",
  "spokenName": "Harry Potter",
  "nameOrder": null,
  "birthDate": "19800731",
  "birthDateSort": "19800731",
  "birthDaySort": "07-31",
  "birthDayFormatted": "31 Jul",
  "birthDateFormatted": "31 Jul 1980",
  "gender": "MALE",
  "genderCode": 1,
  "mrn": null,
  "id": 1000000001,
  "email": "harry.potter@example.com",
  "householdEmail": "harry.potter@example.com",
  "phone": "801-555-4444",
  "householdPhone": "801-555-4444",
  "unitNumber": 200001,
  "unitName": "Gryffindor House Ward",
  "priesthood": null,
  "priesthoodCode": null,
  "priesthoodType": null,
  "age": 40,
  "actualAge": 40,
  "actualAgeInMonths": 487,
  "genderLabelShort": "M",
  "visible": null,
  "nonMember": false,
  "outOfUnitMember": false,
  "notAccountable": false,
  "image": {
    "mediaKey": "abcdef12345678900000000000000000",
    "tokenUrl": "https://ws.churchofjesuschrist.org/api/mlu/scdn/v2/img/12345678-abcd-4ef0-1234-56789abcdef0",
    "format": "JPG",
    "status": "APPROVED",
    "subjectType": "HOUSEHOLD",
    "createdDate": 1572199843153,
    "individualId": 1000000001,
    "unitNumber": 200001,
    "statusEnum": "APPROVED",
    "subjectTypeEnum": "HOUSEHOLD"
  },
  "householdName": "Potter, Harry & Ginevra",
  "legalName": null,
  "individualAndHouseHoldImages": [],
  "editable": false,
  "sustainedDate": null,
  "setApart": false,
  "formattedMrn": null,
  "accountable": true
}
```

## Send Email

```txt
POST /services/umlu/v1/ministering/email?lang=eng
Host lcr.churchofjesuschrist.org

{
  "lang": "eng",
  "allowReplyAll": false,
  "recipients": [1000000001],
  "subject": "You're a Wizard Harry!",
  "messageBody": "<p>Harry, Welcome to the Gryffindor House Ward of the Hogwarts School Stake.</p>",
  "type": "EQ",
}
```

Options

-   `"attachMinisteringAssignment": true`
