# Projects and dependencies analysis

This document provides a comprehensive overview of the projects and their dependencies in the context of upgrading to .NETCoreApp,Version=v10.0.

## Table of Contents

- [Executive Summary](#executive-Summary)
  - [Highlevel Metrics](#highlevel-metrics)
  - [Projects Compatibility](#projects-compatibility)
  - [Package Compatibility](#package-compatibility)
  - [API Compatibility](#api-compatibility)
  - [Binding Redirect Configuration](#binding-redirect-configuration)
- [Aggregate NuGet packages details](#aggregate-nuget-packages-details)
- [Top API Migration Challenges](#top-api-migration-challenges)
  - [Technologies and Features](#technologies-and-features)
  - [Most Frequent API Issues](#most-frequent-api-issues)
- [Projects Relationship Graph](#projects-relationship-graph)
- [Project Details](#project-details)

  - [RiverBooks.AppHost\RiverBooks.AppHost.csproj](#riverbooksapphostriverbooksapphostcsproj)
  - [RiverBooks.Books.Contracts\RiverBooks.Books.Contracts.csproj](#riverbooksbookscontractsriverbooksbookscontractscsproj)
  - [RiverBooks.Books.Tests\RiverBooks.Books.Tests.csproj](#riverbooksbookstestsriverbooksbookstestscsproj)
  - [RiverBooks.Books\RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj)
  - [RiverBooks.EmailSending.Contracts\RiverBooks.EmailSending.Contracts.csproj](#riverbooksemailsendingcontractsriverbooksemailsendingcontractscsproj)
  - [RiverBooks.EmailSending\RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj)
  - [RiverBooks.OrderProcessing.Contracts\RiverBooks.OrderProcessing.Contracts.csproj](#riverbooksorderprocessingcontractsriverbooksorderprocessingcontractscsproj)
  - [RiverBooks.OrderProcessing\RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj)
  - [RiverBooks.OrderProcessingTests\RiverBooks.OrderProcessingTests.csproj](#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj)
  - [RiverBooks.Reporting\RiverBooks.Reporting.csproj](#riverbooksreportingriverbooksreportingcsproj)
  - [RiverBooks.ServiceDefaults\RiverBooks.ServiceDefaults.csproj](#riverbooksservicedefaultsriverbooksservicedefaultscsproj)
  - [RiverBooks.SharedKernel.Tests\RiverBooks.SharedKernel.Tests.csproj](#riverbookssharedkerneltestsriverbookssharedkerneltestscsproj)
  - [RiverBooks.SharedKernel\RiverBooks.SharedKernel.csproj](#riverbookssharedkernelriverbookssharedkernelcsproj)
  - [RiverBooks.Users.Contracts\RiverBooks.Users.Contracts.csproj](#riverbooksuserscontractsriverbooksuserscontractscsproj)
  - [RiverBooks.Users\RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj)
  - [RiverBooks.Web\RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj)


## Executive Summary

### Highlevel Metrics

| Metric | Count | Status |
| :--- | :---: | :--- |
| Total Projects | 16 | 0 require upgrade |
| Total NuGet Packages | 48 | All compatible |
| Total Code Files | 200 |  |
| Total Code Files with Incidents | 0 |  |
| Total Lines of Code | 7947 |  |
| Total Number of Issues | 0 |  |
| Estimated LOC to modify | 0+ | at least 0,0% of codebase |

### Projects Compatibility

| Project | Target Framework | Difficulty | Package Issues | API Issues | Binding Issues | Est. LOC Impact | Description |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| [RiverBooks.AppHost\RiverBooks.AppHost.csproj](#riverbooksapphostriverbooksapphostcsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | DotNetCoreApp, Sdk Style = True |
| [RiverBooks.Books.Contracts\RiverBooks.Books.Contracts.csproj](#riverbooksbookscontractsriverbooksbookscontractscsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | ClassLibrary, Sdk Style = True |
| [RiverBooks.Books.Tests\RiverBooks.Books.Tests.csproj](#riverbooksbookstestsriverbooksbookstestscsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | DotNetCoreApp, Sdk Style = True |
| [RiverBooks.Books\RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | ClassLibrary, Sdk Style = True |
| [RiverBooks.EmailSending.Contracts\RiverBooks.EmailSending.Contracts.csproj](#riverbooksemailsendingcontractsriverbooksemailsendingcontractscsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | ClassLibrary, Sdk Style = True |
| [RiverBooks.EmailSending\RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | ClassLibrary, Sdk Style = True |
| [RiverBooks.OrderProcessing.Contracts\RiverBooks.OrderProcessing.Contracts.csproj](#riverbooksorderprocessingcontractsriverbooksorderprocessingcontractscsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | ClassLibrary, Sdk Style = True |
| [RiverBooks.OrderProcessing\RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | ClassLibrary, Sdk Style = True |
| [RiverBooks.OrderProcessingTests\RiverBooks.OrderProcessingTests.csproj](#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | DotNetCoreApp, Sdk Style = True |
| [RiverBooks.Reporting\RiverBooks.Reporting.csproj](#riverbooksreportingriverbooksreportingcsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | ClassLibrary, Sdk Style = True |
| [RiverBooks.ServiceDefaults\RiverBooks.ServiceDefaults.csproj](#riverbooksservicedefaultsriverbooksservicedefaultscsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | ClassLibrary, Sdk Style = True |
| [RiverBooks.SharedKernel.Tests\RiverBooks.SharedKernel.Tests.csproj](#riverbookssharedkerneltestsriverbookssharedkerneltestscsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | DotNetCoreApp, Sdk Style = True |
| [RiverBooks.SharedKernel\RiverBooks.SharedKernel.csproj](#riverbookssharedkernelriverbookssharedkernelcsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | ClassLibrary, Sdk Style = True |
| [RiverBooks.Users.Contracts\RiverBooks.Users.Contracts.csproj](#riverbooksuserscontractsriverbooksuserscontractscsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | ClassLibrary, Sdk Style = True |
| [RiverBooks.Users\RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | ClassLibrary, Sdk Style = True |
| [RiverBooks.Web\RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj) | net11.0 | ✅ None | 0 | 0 | 0 |  | AspNetCore, Sdk Style = True |

### Package Compatibility

| Status | Count | Percentage |
| :--- | :---: | :---: |
| ✅ Compatible | 48 | 100,0% |
| ⚠️ Incompatible | 0 | 0,0% |
| 🔄 Upgrade Recommended | 0 | 0,0% |
| ***Total NuGet Packages*** | ***48*** | ***100%*** |

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

## Aggregate NuGet packages details

| Package | Current Version | Suggested Version | Projects | Description |
| :--- | :---: | :---: | :--- | :--- |
| Ardalis.GuardClauses | 5.0.0 |  | [RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj)<br/>[RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj)<br/>[RiverBooks.SharedKernel.csproj](#riverbookssharedkernelriverbookssharedkernelcsproj)<br/>[RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj) | ✅Compatible |
| Ardalis.Result | 10.1.0 |  | [RiverBooks.Books.Contracts.csproj](#riverbooksbookscontractsriverbooksbookscontractscsproj)<br/>[RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj)<br/>[RiverBooks.EmailSending.Contracts.csproj](#riverbooksemailsendingcontractsriverbooksemailsendingcontractscsproj)<br/>[RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj)<br/>[RiverBooks.OrderProcessing.Contracts.csproj](#riverbooksorderprocessingcontractsriverbooksorderprocessingcontractscsproj)<br/>[RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj)<br/>[RiverBooks.Reporting.csproj](#riverbooksreportingriverbooksreportingcsproj)<br/>[RiverBooks.SharedKernel.csproj](#riverbookssharedkernelriverbookssharedkernelcsproj)<br/>[RiverBooks.Users.Contracts.csproj](#riverbooksuserscontractsriverbooksuserscontractscsproj)<br/>[RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj) | ✅Compatible |
| Ardalis.Result.AspNetCore | 10.1.0 |  | [RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj) | ✅Compatible |
| Ardalis.Result.FluentValidation | 10.1.0 |  | [RiverBooks.SharedKernel.csproj](#riverbookssharedkernelriverbookssharedkernelcsproj) | ✅Compatible |
| Ardalis.Specification | 9.3.1 |  | [RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj) | ✅Compatible |
| Ardalis.Specification.EntityFrameworkCore | 9.3.1 |  | [RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj) | ✅Compatible |
| Aspire.Hosting.SqlServer | 13.6.5 |  | [RiverBooks.AppHost.csproj](#riverbooksapphostriverbooksapphostcsproj) | ✅Compatible |
| coverlet.collector | 10.1.0 |  | [RiverBooks.Books.Tests.csproj](#riverbooksbookstestsriverbooksbookstestscsproj)<br/>[RiverBooks.OrderProcessingTests.csproj](#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj)<br/>[RiverBooks.SharedKernel.Tests.csproj](#riverbookssharedkerneltestsriverbookssharedkerneltestscsproj) | ✅Compatible |
| Dapper | 2.1.89 |  | [RiverBooks.Reporting.csproj](#riverbooksreportingriverbooksreportingcsproj) | ✅Compatible |
| FastEndpoints | 9.0.0 |  | [RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj)<br/>[RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj)<br/>[RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj)<br/>[RiverBooks.Reporting.csproj](#riverbooksreportingriverbooksreportingcsproj)<br/>[RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj)<br/>[RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj) | ✅Compatible |
| FastEndpoints.Security | 9.0.0 |  | [RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj)<br/>[RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj)<br/>[RiverBooks.Reporting.csproj](#riverbooksreportingriverbooksreportingcsproj)<br/>[RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj)<br/>[RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj) | ✅Compatible |
| FastEndpoints.Swagger | 9.0.0 |  | [RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj) | ✅Compatible |
| FastEndpoints.Testing | 9.0.0 |  | [RiverBooks.Books.Tests.csproj](#riverbooksbookstestsriverbooksbookstestscsproj) | ✅Compatible |
| FluentValidation | 12.2.0 |  | [RiverBooks.SharedKernel.csproj](#riverbookssharedkernelriverbookssharedkernelcsproj) | ✅Compatible |
| MailKit | 5.0.0 |  | [RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj) | ✅Compatible |
| Mediator.Abstractions | 3.0.2 |  | [RiverBooks.Books.Contracts.csproj](#riverbooksbookscontractsriverbooksbookscontractscsproj)<br/>[RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj)<br/>[RiverBooks.EmailSending.Contracts.csproj](#riverbooksemailsendingcontractsriverbooksemailsendingcontractscsproj)<br/>[RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj)<br/>[RiverBooks.OrderProcessing.Contracts.csproj](#riverbooksorderprocessingcontractsriverbooksorderprocessingcontractscsproj)<br/>[RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj)<br/>[RiverBooks.Reporting.csproj](#riverbooksreportingriverbooksreportingcsproj)<br/>[RiverBooks.SharedKernel.csproj](#riverbookssharedkernelriverbookssharedkernelcsproj)<br/>[RiverBooks.Users.Contracts.csproj](#riverbooksuserscontractsriverbooksuserscontractscsproj)<br/>[RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj)<br/>[RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj) | ✅Compatible |
| Mediator.SourceGenerator | 3.0.2 |  | [RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj) | ✅Compatible |
| MessagePack | 3.1.12 |  | [RiverBooks.AppHost.csproj](#riverbooksapphostriverbooksapphostcsproj) | ✅Compatible |
| Microsoft.AspNetCore.Authentication.JwtBearer | 11.0.0 |  | [RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj)<br/>[RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj) | ✅Compatible |
| Microsoft.AspNetCore.Identity.EntityFrameworkCore | 11.0.0 |  | [RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj) | ✅Compatible |
| Microsoft.AspNetCore.OpenApi | 10.0.0 |  | [RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj) | ✅Compatible |
| Microsoft.Data.SqlClient | 7.1.1 |  | [RiverBooks.Reporting.csproj](#riverbooksreportingriverbooksreportingcsproj) | ✅Compatible |
| Microsoft.EntityFrameworkCore | 11.0.0 |  | [RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj)<br/>[RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj)<br/>[RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj) | ✅Compatible |
| Microsoft.EntityFrameworkCore.Design | 10.0.0 |  | [RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj) | ✅Compatible |
| Microsoft.EntityFrameworkCore.Design | 11.0.0 |  | [RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj) | ✅Compatible |
| Microsoft.EntityFrameworkCore.SqlServer | 11.0.0 |  | [RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj)<br/>[RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj)<br/>[RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj) | ✅Compatible |
| Microsoft.Extensions.Http.Resilience | 11.0.0 |  | [RiverBooks.ServiceDefaults.csproj](#riverbooksservicedefaultsriverbooksservicedefaultscsproj) | ✅Compatible |
| Microsoft.Extensions.ServiceDiscovery | 11.0.0 |  | [RiverBooks.ServiceDefaults.csproj](#riverbooksservicedefaultsriverbooksservicedefaultscsproj) | ✅Compatible |
| Microsoft.NET.Test.Sdk | 18.12.0 |  | [RiverBooks.Books.Tests.csproj](#riverbooksbookstestsriverbooksbookstestscsproj)<br/>[RiverBooks.OrderProcessingTests.csproj](#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj)<br/>[RiverBooks.SharedKernel.Tests.csproj](#riverbookssharedkerneltestsriverbookssharedkerneltestscsproj) | ✅Compatible |
| MongoDB.Driver | 3.13.0 |  | [RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj) | ✅Compatible |
| NsDepCop | 3.3.0 |  | [RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj)<br/>[RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj)<br/>[RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj)<br/>[RiverBooks.Reporting.csproj](#riverbooksreportingriverbooksreportingcsproj)<br/>[RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj)<br/>[RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj) | ✅Compatible |
| NSubstitute | 6.2.0 |  | [RiverBooks.OrderProcessingTests.csproj](#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj)<br/>[RiverBooks.SharedKernel.Tests.csproj](#riverbookssharedkerneltestsriverbookssharedkerneltestscsproj) | ✅Compatible |
| OpenTelemetry.Exporter.OpenTelemetryProtocol | 1.21.0 |  | [RiverBooks.ServiceDefaults.csproj](#riverbooksservicedefaultsriverbooksservicedefaultscsproj) | ✅Compatible |
| OpenTelemetry.Extensions.Hosting | 1.21.0 |  | [RiverBooks.ServiceDefaults.csproj](#riverbooksservicedefaultsriverbooksservicedefaultscsproj)<br/>[RiverBooks.SharedKernel.csproj](#riverbookssharedkernelriverbookssharedkernelcsproj) | ✅Compatible |
| OpenTelemetry.Instrumentation.AspNetCore | 1.21.0 |  | [RiverBooks.ServiceDefaults.csproj](#riverbooksservicedefaultsriverbooksservicedefaultscsproj) | ✅Compatible |
| OpenTelemetry.Instrumentation.Http | 1.21.0 |  | [RiverBooks.ServiceDefaults.csproj](#riverbooksservicedefaultsriverbooksservicedefaultscsproj) | ✅Compatible |
| OpenTelemetry.Instrumentation.Runtime | 1.21.0 |  | [RiverBooks.ServiceDefaults.csproj](#riverbooksservicedefaultsriverbooksservicedefaultscsproj) | ✅Compatible |
| Serilog.AspNetCore | 10.0.0 |  | [RiverBooks.Books.csproj](#riverbooksbooksriverbooksbookscsproj)<br/>[RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj)<br/>[RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj)<br/>[RiverBooks.Reporting.csproj](#riverbooksreportingriverbooksreportingcsproj)<br/>[RiverBooks.Users.csproj](#riverbooksusersriverbooksuserscsproj)<br/>[RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj) | ✅Compatible |
| SharpCompress | 1.0.0 |  | [RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj) | ✅Compatible |
| Shouldly | 4.3.0 |  | [RiverBooks.Books.Tests.csproj](#riverbooksbookstestsriverbooksbookstestscsproj)<br/>[RiverBooks.OrderProcessingTests.csproj](#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj)<br/>[RiverBooks.SharedKernel.Tests.csproj](#riverbookssharedkerneltestsriverbookssharedkerneltestscsproj) | ✅Compatible |
| SSH.NET | 2026.0.0 |  | [RiverBooks.Books.Tests.csproj](#riverbooksbookstestsriverbooksbookstestscsproj) | ✅Compatible |
| StackExchange.Redis | 3.4.35 |  | [RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj) | ✅Compatible |
| Swashbuckle.AspNetCore | 10.0.1 |  | [RiverBooks.Web.csproj](#riverbookswebriverbookswebcsproj) | ✅Compatible |
| System.Security.Cryptography.Pkcs | 11.0.0 |  | [RiverBooks.AppHost.csproj](#riverbooksapphostriverbooksapphostcsproj)<br/>[RiverBooks.EmailSending.csproj](#riverbooksemailsendingriverbooksemailsendingcsproj)<br/>[RiverBooks.OrderProcessing.csproj](#riverbooksorderprocessingriverbooksorderprocessingcsproj)<br/>[RiverBooks.Reporting.csproj](#riverbooksreportingriverbooksreportingcsproj) | ✅Compatible |
| Testcontainers.MsSql | 4.16.0 |  | [RiverBooks.Books.Tests.csproj](#riverbooksbookstestsriverbooksbookstestscsproj) | ✅Compatible |
| TngTech.ArchUnitNET.xUnitV3 | 0.13.5 |  | [RiverBooks.OrderProcessingTests.csproj](#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj) | ✅Compatible |
| xunit.runner.visualstudio | 4.0.1 |  | [RiverBooks.Books.Tests.csproj](#riverbooksbookstestsriverbooksbookstestscsproj)<br/>[RiverBooks.OrderProcessingTests.csproj](#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj)<br/>[RiverBooks.SharedKernel.Tests.csproj](#riverbookssharedkerneltestsriverbookssharedkerneltestscsproj) | ✅Compatible |
| xunit.v3.mtp-off | 4.0.3 |  | [RiverBooks.Books.Tests.csproj](#riverbooksbookstestsriverbooksbookstestscsproj)<br/>[RiverBooks.OrderProcessingTests.csproj](#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj)<br/>[RiverBooks.SharedKernel.Tests.csproj](#riverbookssharedkerneltestsriverbookssharedkerneltestscsproj) | ✅Compatible |

## Top API Migration Challenges

### Technologies and Features

| Technology | Issues | Percentage | Migration Path |
| :--- | :---: | :---: | :--- |

### Most Frequent API Issues

| API | Count | Percentage | Category |
| :--- | :---: | :---: | :--- |

## Projects Relationship Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart LR
    P1["<b>📦&nbsp;RiverBooks.AppHost.csproj</b><br/><small>net11.0</small>"]
    P2["<b>📦&nbsp;RiverBooks.ServiceDefaults.csproj</b><br/><small>net11.0</small>"]
    P3["<b>📦&nbsp;RiverBooks.SharedKernel.Tests.csproj</b><br/><small>net11.0</small>"]
    P4["<b>📦&nbsp;RiverBooks.SharedKernel.csproj</b><br/><small>net11.0</small>"]
    P5["<b>📦&nbsp;RiverBooks.Web.csproj</b><br/><small>net11.0</small>"]
    P6["<b>📦&nbsp;RiverBooks.Books.Contracts.csproj</b><br/><small>net11.0</small>"]
    P7["<b>📦&nbsp;RiverBooks.Books.Tests.csproj</b><br/><small>net11.0</small>"]
    P8["<b>📦&nbsp;RiverBooks.Books.csproj</b><br/><small>net11.0</small>"]
    P9["<b>📦&nbsp;RiverBooks.EmailSending.Contracts.csproj</b><br/><small>net11.0</small>"]
    P10["<b>📦&nbsp;RiverBooks.EmailSending.csproj</b><br/><small>net11.0</small>"]
    P11["<b>📦&nbsp;RiverBooks.OrderProcessing.Contracts.csproj</b><br/><small>net11.0</small>"]
    P12["<b>📦&nbsp;RiverBooks.OrderProcessing.csproj</b><br/><small>net11.0</small>"]
    P13["<b>📦&nbsp;RiverBooks.OrderProcessingTests.csproj</b><br/><small>net11.0</small>"]
    P14["<b>📦&nbsp;RiverBooks.Reporting.csproj</b><br/><small>net11.0</small>"]
    P15["<b>📦&nbsp;RiverBooks.Users.Contracts.csproj</b><br/><small>net11.0</small>"]
    P16["<b>📦&nbsp;RiverBooks.Users.csproj</b><br/><small>net11.0</small>"]
    P1 --> P5
    P3 --> P4
    P5 --> P12
    P5 --> P16
    P5 --> P10
    P5 --> P4
    P5 --> P14
    P5 --> P2
    P5 --> P8
    P7 --> P5
    P8 --> P6
    P10 --> P9
    P12 --> P9
    P12 --> P15
    P12 --> P11
    P13 --> P12
    P14 --> P6
    P14 --> P11
    P15 --> P4
    P16 --> P9
    P16 --> P15
    P16 --> P6
    P16 --> P11
    click P1 "#riverbooksapphostriverbooksapphostcsproj"
    click P2 "#riverbooksservicedefaultsriverbooksservicedefaultscsproj"
    click P3 "#riverbookssharedkerneltestsriverbookssharedkerneltestscsproj"
    click P4 "#riverbookssharedkernelriverbookssharedkernelcsproj"
    click P5 "#riverbookswebriverbookswebcsproj"
    click P6 "#riverbooksbookscontractsriverbooksbookscontractscsproj"
    click P7 "#riverbooksbookstestsriverbooksbookstestscsproj"
    click P8 "#riverbooksbooksriverbooksbookscsproj"
    click P9 "#riverbooksemailsendingcontractsriverbooksemailsendingcontractscsproj"
    click P10 "#riverbooksemailsendingriverbooksemailsendingcsproj"
    click P11 "#riverbooksorderprocessingcontractsriverbooksorderprocessingcontractscsproj"
    click P12 "#riverbooksorderprocessingriverbooksorderprocessingcsproj"
    click P13 "#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj"
    click P14 "#riverbooksreportingriverbooksreportingcsproj"
    click P15 "#riverbooksuserscontractsriverbooksuserscontractscsproj"
    click P16 "#riverbooksusersriverbooksuserscsproj"

```

## Project Details

<a id="riverbooksapphostriverbooksapphostcsproj"></a>
### RiverBooks.AppHost\RiverBooks.AppHost.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** DotNetCoreApp
- **Dependencies**: 1
- **Dependants**: 0
- **Number of Files**: 1
- **Lines of Code**: 24
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph current["RiverBooks.AppHost.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.AppHost.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksapphostriverbooksapphostcsproj"
    end
    subgraph downstream["Dependencies (1"]
        P5["<b>📦&nbsp;RiverBooks.Web.csproj</b><br/><small>net11.0</small>"]
        click P5 "#riverbookswebriverbookswebcsproj"
    end
    MAIN --> P5

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksbookscontractsriverbooksbookscontractscsproj"></a>
### RiverBooks.Books.Contracts\RiverBooks.Books.Contracts.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** ClassLibrary
- **Dependencies**: 0
- **Dependants**: 3
- **Number of Files**: 2
- **Lines of Code**: 10
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (3)"]
        P8["<b>📦&nbsp;RiverBooks.Books.csproj</b><br/><small>net11.0</small>"]
        P14["<b>📦&nbsp;RiverBooks.Reporting.csproj</b><br/><small>net11.0</small>"]
        P16["<b>📦&nbsp;RiverBooks.Users.csproj</b><br/><small>net11.0</small>"]
        click P8 "#riverbooksbooksriverbooksbookscsproj"
        click P14 "#riverbooksreportingriverbooksreportingcsproj"
        click P16 "#riverbooksusersriverbooksuserscsproj"
    end
    subgraph current["RiverBooks.Books.Contracts.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.Books.Contracts.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksbookscontractsriverbooksbookscontractscsproj"
    end
    P8 --> MAIN
    P14 --> MAIN
    P16 --> MAIN

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksbookstestsriverbooksbookstestscsproj"></a>
### RiverBooks.Books.Tests\RiverBooks.Books.Tests.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** DotNetCoreApp
- **Dependencies**: 1
- **Dependants**: 0
- **Number of Files**: 6
- **Lines of Code**: 221
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph current["RiverBooks.Books.Tests.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.Books.Tests.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksbookstestsriverbooksbookstestscsproj"
    end
    subgraph downstream["Dependencies (1"]
        P5["<b>📦&nbsp;RiverBooks.Web.csproj</b><br/><small>net11.0</small>"]
        click P5 "#riverbookswebriverbookswebcsproj"
    end
    MAIN --> P5

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksbooksriverbooksbookscsproj"></a>
### RiverBooks.Books\RiverBooks.Books.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** ClassLibrary
- **Dependencies**: 1
- **Dependants**: 1
- **Number of Files**: 28
- **Lines of Code**: 693
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (1)"]
        P5["<b>📦&nbsp;RiverBooks.Web.csproj</b><br/><small>net11.0</small>"]
        click P5 "#riverbookswebriverbookswebcsproj"
    end
    subgraph current["RiverBooks.Books.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.Books.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksbooksriverbooksbookscsproj"
    end
    subgraph downstream["Dependencies (1"]
        P6["<b>📦&nbsp;RiverBooks.Books.Contracts.csproj</b><br/><small>net11.0</small>"]
        click P6 "#riverbooksbookscontractsriverbooksbookscontractscsproj"
    end
    P5 --> MAIN
    MAIN --> P6

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksemailsendingcontractsriverbooksemailsendingcontractscsproj"></a>
### RiverBooks.EmailSending.Contracts\RiverBooks.EmailSending.Contracts.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** ClassLibrary
- **Dependencies**: 0
- **Dependants**: 3
- **Number of Files**: 1
- **Lines of Code**: 12
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (3)"]
        P10["<b>📦&nbsp;RiverBooks.EmailSending.csproj</b><br/><small>net11.0</small>"]
        P12["<b>📦&nbsp;RiverBooks.OrderProcessing.csproj</b><br/><small>net11.0</small>"]
        P16["<b>📦&nbsp;RiverBooks.Users.csproj</b><br/><small>net11.0</small>"]
        click P10 "#riverbooksemailsendingriverbooksemailsendingcsproj"
        click P12 "#riverbooksorderprocessingriverbooksorderprocessingcsproj"
        click P16 "#riverbooksusersriverbooksuserscsproj"
    end
    subgraph current["RiverBooks.EmailSending.Contracts.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.EmailSending.Contracts.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksemailsendingcontractsriverbooksemailsendingcontractscsproj"
    end
    P10 --> MAIN
    P12 --> MAIN
    P16 --> MAIN

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksemailsendingriverbooksemailsendingcsproj"></a>
### RiverBooks.EmailSending\RiverBooks.EmailSending.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** ClassLibrary
- **Dependencies**: 1
- **Dependants**: 1
- **Number of Files**: 13
- **Lines of Code**: 358
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (1)"]
        P5["<b>📦&nbsp;RiverBooks.Web.csproj</b><br/><small>net11.0</small>"]
        click P5 "#riverbookswebriverbookswebcsproj"
    end
    subgraph current["RiverBooks.EmailSending.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.EmailSending.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksemailsendingriverbooksemailsendingcsproj"
    end
    subgraph downstream["Dependencies (1"]
        P9["<b>📦&nbsp;RiverBooks.EmailSending.Contracts.csproj</b><br/><small>net11.0</small>"]
        click P9 "#riverbooksemailsendingcontractsriverbooksemailsendingcontractscsproj"
    end
    P5 --> MAIN
    MAIN --> P9

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksorderprocessingcontractsriverbooksorderprocessingcontractscsproj"></a>
### RiverBooks.OrderProcessing.Contracts\RiverBooks.OrderProcessing.Contracts.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** ClassLibrary
- **Dependencies**: 0
- **Dependants**: 3
- **Number of Files**: 5
- **Lines of Code**: 48
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (3)"]
        P12["<b>📦&nbsp;RiverBooks.OrderProcessing.csproj</b><br/><small>net11.0</small>"]
        P14["<b>📦&nbsp;RiverBooks.Reporting.csproj</b><br/><small>net11.0</small>"]
        P16["<b>📦&nbsp;RiverBooks.Users.csproj</b><br/><small>net11.0</small>"]
        click P12 "#riverbooksorderprocessingriverbooksorderprocessingcsproj"
        click P14 "#riverbooksreportingriverbooksreportingcsproj"
        click P16 "#riverbooksusersriverbooksuserscsproj"
    end
    subgraph current["RiverBooks.OrderProcessing.Contracts.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.OrderProcessing.Contracts.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksorderprocessingcontractsriverbooksorderprocessingcontractscsproj"
    end
    P12 --> MAIN
    P14 --> MAIN
    P16 --> MAIN

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksorderprocessingriverbooksorderprocessingcsproj"></a>
### RiverBooks.OrderProcessing\RiverBooks.OrderProcessing.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** ClassLibrary
- **Dependencies**: 3
- **Dependants**: 2
- **Number of Files**: 39
- **Lines of Code**: 1443
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (2)"]
        P5["<b>📦&nbsp;RiverBooks.Web.csproj</b><br/><small>net11.0</small>"]
        P13["<b>📦&nbsp;RiverBooks.OrderProcessingTests.csproj</b><br/><small>net11.0</small>"]
        click P5 "#riverbookswebriverbookswebcsproj"
        click P13 "#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj"
    end
    subgraph current["RiverBooks.OrderProcessing.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.OrderProcessing.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksorderprocessingriverbooksorderprocessingcsproj"
    end
    subgraph downstream["Dependencies (3"]
        P9["<b>📦&nbsp;RiverBooks.EmailSending.Contracts.csproj</b><br/><small>net11.0</small>"]
        P15["<b>📦&nbsp;RiverBooks.Users.Contracts.csproj</b><br/><small>net11.0</small>"]
        P11["<b>📦&nbsp;RiverBooks.OrderProcessing.Contracts.csproj</b><br/><small>net11.0</small>"]
        click P9 "#riverbooksemailsendingcontractsriverbooksemailsendingcontractscsproj"
        click P15 "#riverbooksuserscontractsriverbooksuserscontractscsproj"
        click P11 "#riverbooksorderprocessingcontractsriverbooksorderprocessingcontractscsproj"
    end
    P5 --> MAIN
    P13 --> MAIN
    MAIN --> P9
    MAIN --> P15
    MAIN --> P11

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj"></a>
### RiverBooks.OrderProcessingTests\RiverBooks.OrderProcessingTests.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** DotNetCoreApp
- **Dependencies**: 1
- **Dependants**: 0
- **Number of Files**: 8
- **Lines of Code**: 819
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph current["RiverBooks.OrderProcessingTests.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.OrderProcessingTests.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksorderprocessingtestsriverbooksorderprocessingtestscsproj"
    end
    subgraph downstream["Dependencies (1"]
        P12["<b>📦&nbsp;RiverBooks.OrderProcessing.csproj</b><br/><small>net11.0</small>"]
        click P12 "#riverbooksorderprocessingriverbooksorderprocessingcsproj"
    end
    MAIN --> P12

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksreportingriverbooksreportingcsproj"></a>
### RiverBooks.Reporting\RiverBooks.Reporting.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** ClassLibrary
- **Dependencies**: 2
- **Dependants**: 1
- **Number of Files**: 14
- **Lines of Code**: 376
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (1)"]
        P5["<b>📦&nbsp;RiverBooks.Web.csproj</b><br/><small>net11.0</small>"]
        click P5 "#riverbookswebriverbookswebcsproj"
    end
    subgraph current["RiverBooks.Reporting.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.Reporting.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksreportingriverbooksreportingcsproj"
    end
    subgraph downstream["Dependencies (2"]
        P6["<b>📦&nbsp;RiverBooks.Books.Contracts.csproj</b><br/><small>net11.0</small>"]
        P11["<b>📦&nbsp;RiverBooks.OrderProcessing.Contracts.csproj</b><br/><small>net11.0</small>"]
        click P6 "#riverbooksbookscontractsriverbooksbookscontractscsproj"
        click P11 "#riverbooksorderprocessingcontractsriverbooksorderprocessingcontractscsproj"
    end
    P5 --> MAIN
    MAIN --> P6
    MAIN --> P11

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksservicedefaultsriverbooksservicedefaultscsproj"></a>
### RiverBooks.ServiceDefaults\RiverBooks.ServiceDefaults.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** ClassLibrary
- **Dependencies**: 0
- **Dependants**: 1
- **Number of Files**: 1
- **Lines of Code**: 127
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (1)"]
        P5["<b>📦&nbsp;RiverBooks.Web.csproj</b><br/><small>net11.0</small>"]
        click P5 "#riverbookswebriverbookswebcsproj"
    end
    subgraph current["RiverBooks.ServiceDefaults.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.ServiceDefaults.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksservicedefaultsriverbooksservicedefaultscsproj"
    end
    P5 --> MAIN

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbookssharedkerneltestsriverbookssharedkerneltestscsproj"></a>
### RiverBooks.SharedKernel.Tests\RiverBooks.SharedKernel.Tests.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** DotNetCoreApp
- **Dependencies**: 1
- **Dependants**: 0
- **Number of Files**: 3
- **Lines of Code**: 158
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph current["RiverBooks.SharedKernel.Tests.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.SharedKernel.Tests.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbookssharedkerneltestsriverbookssharedkerneltestscsproj"
    end
    subgraph downstream["Dependencies (1"]
        P4["<b>📦&nbsp;RiverBooks.SharedKernel.csproj</b><br/><small>net11.0</small>"]
        click P4 "#riverbookssharedkernelriverbookssharedkernelcsproj"
    end
    MAIN --> P4

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbookssharedkernelriverbookssharedkernelcsproj"></a>
### RiverBooks.SharedKernel\RiverBooks.SharedKernel.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** ClassLibrary
- **Dependencies**: 0
- **Dependants**: 3
- **Number of Files**: 9
- **Lines of Code**: 320
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (3)"]
        P3["<b>📦&nbsp;RiverBooks.SharedKernel.Tests.csproj</b><br/><small>net11.0</small>"]
        P5["<b>📦&nbsp;RiverBooks.Web.csproj</b><br/><small>net11.0</small>"]
        P15["<b>📦&nbsp;RiverBooks.Users.Contracts.csproj</b><br/><small>net11.0</small>"]
        click P3 "#riverbookssharedkerneltestsriverbookssharedkerneltestscsproj"
        click P5 "#riverbookswebriverbookswebcsproj"
        click P15 "#riverbooksuserscontractsriverbooksuserscontractscsproj"
    end
    subgraph current["RiverBooks.SharedKernel.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.SharedKernel.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbookssharedkernelriverbookssharedkernelcsproj"
    end
    P3 --> MAIN
    P5 --> MAIN
    P15 --> MAIN

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksuserscontractsriverbooksuserscontractscsproj"></a>
### RiverBooks.Users.Contracts\RiverBooks.Users.Contracts.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** ClassLibrary
- **Dependencies**: 1
- **Dependants**: 2
- **Number of Files**: 6
- **Lines of Code**: 45
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (2)"]
        P12["<b>📦&nbsp;RiverBooks.OrderProcessing.csproj</b><br/><small>net11.0</small>"]
        P16["<b>📦&nbsp;RiverBooks.Users.csproj</b><br/><small>net11.0</small>"]
        click P12 "#riverbooksorderprocessingriverbooksorderprocessingcsproj"
        click P16 "#riverbooksusersriverbooksuserscsproj"
    end
    subgraph current["RiverBooks.Users.Contracts.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.Users.Contracts.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksuserscontractsriverbooksuserscontractscsproj"
    end
    subgraph downstream["Dependencies (1"]
        P4["<b>📦&nbsp;RiverBooks.SharedKernel.csproj</b><br/><small>net11.0</small>"]
        click P4 "#riverbookssharedkernelriverbookssharedkernelcsproj"
    end
    P12 --> MAIN
    P16 --> MAIN
    MAIN --> P4

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbooksusersriverbooksuserscsproj"></a>
### RiverBooks.Users\RiverBooks.Users.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** ClassLibrary
- **Dependencies**: 4
- **Dependants**: 1
- **Number of Files**: 63
- **Lines of Code**: 3189
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (1)"]
        P5["<b>📦&nbsp;RiverBooks.Web.csproj</b><br/><small>net11.0</small>"]
        click P5 "#riverbookswebriverbookswebcsproj"
    end
    subgraph current["RiverBooks.Users.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.Users.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbooksusersriverbooksuserscsproj"
    end
    subgraph downstream["Dependencies (4"]
        P9["<b>📦&nbsp;RiverBooks.EmailSending.Contracts.csproj</b><br/><small>net11.0</small>"]
        P15["<b>📦&nbsp;RiverBooks.Users.Contracts.csproj</b><br/><small>net11.0</small>"]
        P6["<b>📦&nbsp;RiverBooks.Books.Contracts.csproj</b><br/><small>net11.0</small>"]
        P11["<b>📦&nbsp;RiverBooks.OrderProcessing.Contracts.csproj</b><br/><small>net11.0</small>"]
        click P9 "#riverbooksemailsendingcontractsriverbooksemailsendingcontractscsproj"
        click P15 "#riverbooksuserscontractsriverbooksuserscontractscsproj"
        click P6 "#riverbooksbookscontractsriverbooksbookscontractscsproj"
        click P11 "#riverbooksorderprocessingcontractsriverbooksorderprocessingcontractscsproj"
    end
    P5 --> MAIN
    MAIN --> P9
    MAIN --> P15
    MAIN --> P6
    MAIN --> P11

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

<a id="riverbookswebriverbookswebcsproj"></a>
### RiverBooks.Web\RiverBooks.Web.csproj

#### Project Info

- **Current Target Framework:** net11.0✅
- **SDK-style**: True
- **Project Kind:** AspNetCore
- **Dependencies**: 7
- **Dependants**: 2
- **Number of Files**: 6
- **Lines of Code**: 104
- **Estimated LOC to modify**: 0+ (at least 0,0% of the project)

#### Dependency Graph

Legend:
📦 SDK-style project
⚙️ Classic project

```mermaid
flowchart TB
    subgraph upstream["Dependants (2)"]
        P1["<b>📦&nbsp;RiverBooks.AppHost.csproj</b><br/><small>net11.0</small>"]
        P7["<b>📦&nbsp;RiverBooks.Books.Tests.csproj</b><br/><small>net11.0</small>"]
        click P1 "#riverbooksapphostriverbooksapphostcsproj"
        click P7 "#riverbooksbookstestsriverbooksbookstestscsproj"
    end
    subgraph current["RiverBooks.Web.csproj"]
        MAIN["<b>📦&nbsp;RiverBooks.Web.csproj</b><br/><small>net11.0</small>"]
        click MAIN "#riverbookswebriverbookswebcsproj"
    end
    subgraph downstream["Dependencies (7"]
        P12["<b>📦&nbsp;RiverBooks.OrderProcessing.csproj</b><br/><small>net11.0</small>"]
        P16["<b>📦&nbsp;RiverBooks.Users.csproj</b><br/><small>net11.0</small>"]
        P10["<b>📦&nbsp;RiverBooks.EmailSending.csproj</b><br/><small>net11.0</small>"]
        P4["<b>📦&nbsp;RiverBooks.SharedKernel.csproj</b><br/><small>net11.0</small>"]
        P14["<b>📦&nbsp;RiverBooks.Reporting.csproj</b><br/><small>net11.0</small>"]
        P2["<b>📦&nbsp;RiverBooks.ServiceDefaults.csproj</b><br/><small>net11.0</small>"]
        P8["<b>📦&nbsp;RiverBooks.Books.csproj</b><br/><small>net11.0</small>"]
        click P12 "#riverbooksorderprocessingriverbooksorderprocessingcsproj"
        click P16 "#riverbooksusersriverbooksuserscsproj"
        click P10 "#riverbooksemailsendingriverbooksemailsendingcsproj"
        click P4 "#riverbookssharedkernelriverbookssharedkernelcsproj"
        click P14 "#riverbooksreportingriverbooksreportingcsproj"
        click P2 "#riverbooksservicedefaultsriverbooksservicedefaultscsproj"
        click P8 "#riverbooksbooksriverbooksbookscsproj"
    end
    P1 --> MAIN
    P7 --> MAIN
    MAIN --> P12
    MAIN --> P16
    MAIN --> P10
    MAIN --> P4
    MAIN --> P14
    MAIN --> P2
    MAIN --> P8

```

### API Compatibility

| Category | Count | Impact |
| :--- | :---: | :--- |
| 🔴 Binary Incompatible | 0 | High - Require code changes |
| 🟡 Source Incompatible | 0 | Medium - Needs re-compilation and potential conflicting API error fixing |
| 🔵 Behavioral change | 0 | Low - Behavioral changes that may require testing at runtime |
| ✅ Compatible | 0 |  |
| ***Total APIs Analyzed*** | ***0*** |  |

