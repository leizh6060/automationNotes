[ Clients / Users ] 
        │
        ▼ (HTTPS / REST)
┌──────────────────────────────────────────────┐
│       Azure API Management (APIM)            │ ◄── [Policies / Security / Rate Limiting]
└──────────────────────┬───────────────────────┘
                       │
         ┌─────────────┴─────────────┐
         ▼                           ▼
┌──────────────────┐        ┌──────────────────┐
│  Event-Driven    │        │  Message-Driven  │
│    Solutions     │        │    Solutions     │
└────────┬─────────┘        └────────┬─────────┘
         │                           │
   ┌─────┴─────┐               ┌─────┴─────┐
   ▼           ▼               ▼           ▼
[Event      [Event           [Service    [Queue
 Grid]      Hubs]             Bus]      Storage]
   │           │               │           │
   └─────┬─────┘               └─────┬─────┘
         ▼                           ▼
┌──────────────────────────────────────────────┐
│         Azure Compute (Functions / Apps)     │
└──────────────────────────────────────────────┘
