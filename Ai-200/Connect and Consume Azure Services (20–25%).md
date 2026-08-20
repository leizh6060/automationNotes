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
Azure API Management is made up of an API _gateway_, a _management plane_, and a _developer portal_, with features designed for different audiences in the API ecosystem.
# Azure API Management Deep Dive
https://www.youtube.com/watch?v=PXtFq5wmGt0&t=3245s

#### Develop event- and message-based AI solutions

- Queue and process back-end operations by using Azure Service Bus, including dead-letter queue handling, messages, topics, and subscriptions
    
- Implement event-driven workflows by using Azure Event Grid, including filters, custom events, and retries
    

[](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ai-200#develop-and-implement-azure-functions)

#### Develop and implement Azure Functions

- Build serverless APIs, including implementing triggers and bindings
    
- Configure and deploy function apps


# Observe and troubleshoot apps on Azure
Observability rests on three pillars that each provide a different perspective on system behavior:

- **Distributed tracing:** Captures the full path of a request as it moves through services. Traces show you the sequence and timing of operations, making it possible to identify exactly where delays or errors occur. Tracing is the primary focus of this module.
- **Metrics:** Provide aggregate numerical measurements over time, such as request counts, error rates, and response-time percentiles. Metrics help you detect trends and set alerting thresholds for service-level objectives.
- **Logs:** Capture detailed, timestamped records of discrete events within a service. Logs provide the granular detail needed to understand why a specific operation behaved the way it did.
## Choose an instrumentation approach
**Autoinstrumentation** enables telemetry collection through configuration without modifying application code.
**Manual instrumentation** uses the OpenTelemetry SDK embedded in your application code.



# Manage application secrets and configuration for AI solutions
# Azure Key Vault Deep Dive (AZ-500)

[![John Savill's Technical Training](https://yt3.ggpht.com/CMNReqFEhQAL1foeh3s3-OySr0oS3j2UZGpoCUsJJNZFK-dxvjMEXze_tOHXlDjOshSDZwX0=s88-c-k-c0x00ffffff-no-rj)](https://www.youtube.com/@NTFAQGuy)

[John Savill's Technical Training](https://www.youtube.com/@NTFAQGuy)


# Manage application settings with Azure App Configuration
# Azure App Configuration Tutorial

[![Adam Marczak - Azure for Everyone](https://yt3.ggpht.com/YNdmz7p9f-ShKJVzq9ekFiB0kfbrUpBaG5ggqzUQKQLHRcsqOvNgSN_fABnKQCsVSxMGzbpNwA=s88-c-k-c0x00ffffff-no-rj)](https://www.youtube.com/@AdamMarczakYT)

[Adam Marczak -](https://www.youtube.com/@AdamMarczakYT)

Service Bus
# Azure Service Bus Explained | Why It Exists + Simple C# Demo
https://www.youtube.com/watch?v=L2aPzOULsXU