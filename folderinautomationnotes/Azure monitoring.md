 from kimi
 ┌─────────────────────────────────────────────────────────────────┐
│                        Data Sources                              │
├─────────────┬─────────────┬─────────────┬─────────────┬─────────┤
│  Applications│   VMs &     │  Containers │  Networking │ Custom  │
│  (App Insights)│  OS (Agent) │  (AKS/ACI)  │  (NSG/VNet) │ Sources │
└──────┬──────┴──────┬──────┴──────┬──────┴──────┬──────┴────┬────┘
       │             │             │             │           │
       └─────────────┴──────┬──────┴─────────────┘           │
                            ▼                                │
              ┌─────────────────────────┐                   │
              │   Azure Monitor         │                   │
              │   ─────────────────     │                   │
              │   • Metrics (Numeric)   │◄──────────────────┘
              │   • Logs (Structured)   │
              │   • Traces (Distributed)  │
              │   • Alerts & Actions      │
              └───────────┬─────────────┘
                          │
        ┌─────────────────┼─────────────────┐
        ▼                 ▼                 ▼
┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│  Analyze     │  │  Visualize   │  │  Respond     │
│              │  │              │  │              │
│ • Log Analytics│  │ • Dashboards │  │ • Alerts     │
│ • KQL Queries │  │ • Workbooks  │  │ • Auto-scale │
│ • Insights    │  │ • Grafana    │  │ • Logic Apps │
│ • Analytics   │  │ • Power BI   │  │ • Webhooks   │
└──────────────┘  └──────────────┘  └──────────────┘
https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview
