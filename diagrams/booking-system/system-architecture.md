# Appointment Booking System

## System Architecture

```mermaid
flowchart TB
    subgraph Actors["👥 Actors"]
        Customer[Customer<br/>PWA Mobile/Desktop]
        Staff[Staff User<br/>Back Office]
        SuperAdmin[Super Admin]
    end

    subgraph Edge["📱 Static Hosting + CDN"]
        ReactApp[React PWA<br/>Vite Build]
        subgraph UI["UI Layer"]
            Calendar[Calendar View<br/>Availability Slots]
            BookingForm[Booking Form]
            ResourceMgmt[Resource Management]
            AdminUI[Admin Dashboard]
        end
    end

    subgraph Workers["⚡ Edge Workers API"]
        Framework[HTTP Framework]
        subgraph MW["Middleware"]
            AuthMW[Auth Middleware<br/>JWT + RBAC]
            RateLimit[Rate Limiting]
        end
        subgraph Routes["API Routes"]
            BookingRoutes[Booking Routes]
            ResourceRoutes[Resource Routes]
            ScheduleRoutes[Schedule Routes]
            TenantRoutes[Tenant Routes]
        end
        subgraph Logic["Business Logic"]
            AvailCalc[Availability Calculator]
            ConflictCheck[Overlap Detection]
            SlotGen[Time Slot Generator]
        end
    end

    subgraph DataLayer["☁️ Edge Data"]
        D1[(SQL Database)]
        KV[Key-Value Cache<br/>Availability Slots]
        R2[Object Storage<br/>Images]
    end

    subgraph Shared["📦 Shared Package"]
        Types[TypeScript Types]
        Schemas[Validation Schemas]
    end

    Customer --> ReactApp
    Staff --> ReactApp
    SuperAdmin --> ReactApp

    ReactApp -->|REST API| Framework
    Framework --> MW --> Routes
    Routes --> Logic

    Logic --> D1
    Logic --> KV
    BookingRoutes --> ConflictCheck
    ScheduleRoutes --> AvailCalc
    AvailCalc --> SlotGen

    ResourceRoutes --> R2
    AvailCalc --> KV

    Shared -.-> ReactApp
    Shared -.-> Framework

    style Actors fill:#e3f2fd,stroke:#1565c0
    style Edge fill:#e8f5e9,stroke:#2e7d32
    style Workers fill:#fff3e0,stroke:#e65100
    style DataLayer fill:#f3e5f5,stroke:#7b1fa2
    style Shared fill:#e0f7fa,stroke:#00838f
    style UI fill:#e8f5e9,stroke:#388e3c
    style MW fill:#fff8e1,stroke:#f57f17
    style Routes fill:#fff3e0,stroke:#ef6c00
    style Logic fill:#fff3e0,stroke:#ff8f00
```
