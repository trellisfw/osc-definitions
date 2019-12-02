# OSC Definitions
> Oblivious Smart Contracts Definitions

## Sustainable Fishing

### OSC Objective
The global fishing industry would like to eliminate over-fishing by requiring fishing vessels to catch fish only in approved areas.  This OSC pulls a set of approved geospatial catch boundaries from an industry list, intersects the catch locations with the boundaries, and produces a PAC with the time period or lot number, a “true/false” answer about whether all the catch locations fit within the boundaries, and a cryptographic proof that the OSC was executed faithfully. 

#### OSC JSON Template 

```javascript
{
  "oscid": {
    "codebase": "sustainablefishing-v1.0.0",
    "pac": "sustainablefishing-v1.0.0",
    "definition": "https://github.com/trellisfw/osc-definitions"
  },
  "timestamp": "2019-08-14T02:38:32.921Z",
  "lot": "12345",
  "organization": {
    "name": "Bob's Fishing Boat"
  },
  "certification_status": "passed",
  "certified_quantity": { "value": "25", "units": "tons" },
  "certified_product": "tuna", 
  "attestations": {
    "caught_within_sustainable_boundaries": true
  },
  "signatures": [
     {
       "quote": {
         "report": "<base64 encoded report>",
         "mrsigner": "<base64 encoded mrsigner>",
         "mrenclave": "<base64 encoded mrenclave",
         "user_data": "<base64 encoded user data, understood to be hash of PAC> ",
         "value": "<base64 encoded entire quote>"
       }
     }
  ],
  "data_hash": {
    "value": "e493999f59c6537c3bc674fb5d5fac6d6437e546fe202025591dee0625ee9bc9",
    "alg": "SHA-256"
  }
}
```

#### OSC JSON Template for Trellis++ Broker
```javascript
{
  "id": "316c9712-5e51-4267-8891-859b6a7cc3b7",
  "oscid": {
    "codebase": "massbalance-v1.0.0",
    "pac": "massbalance-v1.0.0",
    "definition": "https://github.com/trellisfw/osc-definitions"
  },
  "label": "MB",
  "title": "Organic Mass Balance",
  "osc_hash": {
    "value": "e866b9393619261cd329cc1198d8e188c62ada321b01c8492ab7513f86510d7a",
    "alg": "SHA-256"
  },
  "date_init": "09.17.2019",
  "timestamp": "2019-08-14T02:38:32.921Z",
  "trustLevel": "tl3",
   "organization": {
    "name": "Bob's Mass Balance"
  },
  "broker_signals":{
    "restart": false,
    "init_ra": false,
    "turnoff": false,
    "generate_pac": true,
    "privateData": "all",
    "token": "servio"
  },
  "generatedPACs": {
    "pacrandomid1": {},
    "pacrandomid2": {}
  },
  "blockchain_config": {
    "host": "string"
  }
}
```

