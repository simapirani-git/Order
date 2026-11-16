# Order - .NET Web API

## Introduction

Order is an ASP.NET Core Web API developed as part of a Multi-Repository architecture.

The project demonstrates how an independent .NET application can consume reusable components distributed through a NuGet package hosted in Azure DevOps Artifacts.

Order uses the Shared class library to promote code reuse and centralized dependency management across independent applications.

## Project Architecture

Order is one of three independent application repositories in this project:

| Repository | Responsibility |
|---|---|
| Shared | Reusable .NET Class Library |
| Basket | Basket Web API |
| Identity | Identity Web API |
| Order | Order Web API |

Each repository maintains its own solution, project structure, source code, Git history, and CI/CD pipeline.

## Technologies Used

- C#
- .NET 10
- ASP.NET Core Web API
- NuGet Package Management
- Azure DevOps Artifacts
- Azure DevOps Classic Pipelines
- Git and GitHub

## Repository Structure

```text
Order/
│
├── src/
│   └── Order/
│       ├── Controllers/
│       ├── Properties/
│       ├── Order.csproj
│       ├── Order.http
│       ├── Program.cs
│       ├── WeatherForecast.cs
│       └── appsettings.json
│
├── .gitignore
├── Order.slnx
└── README.md
```

## Shared NuGet Package Integration

Order consumes the Shared class library through a NuGet package published to Azure DevOps Artifacts.

The package is available through the `Shared-Feed` feed.

This integration demonstrates:

- Reusable code across independent repositories.
- Centralized package distribution.
- Version-based dependency management.
- Reduced code duplication.
- Independent application development.

## Build and Run

Restore dependencies:

```bash
dotnet restore Order.slnx
```

Build the solution:

```bash
dotnet build Order.slnx
```

Run the application:

```bash
dotnet run --project src/Order/Order.csproj
```

## CI/CD Pipeline

The Order repository is integrated with Azure DevOps Classic Pipelines.

The pipeline includes the following stages:

1. NuGet Restore
2. Build
3. Test
4. Pack
5. Push NuGet Package (where applicable)
6. Publish Build Artifact

These stages automate dependency restoration, application validation, and build artifact generation.

## Project Objectives

- Demonstrate independent repository management.
- Implement a Multi-Repository architecture.
- Consume reusable NuGet packages.
- Integrate Azure DevOps Artifacts with .NET applications.
- Implement automated CI/CD workflows.
- Maintain independent application lifecycle and version control.

---

**Note:** This repository is part of a personal learning and demonstration project using sample configurations and data.
