---
title: Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker standard basierend)
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3c9a4bec4f48d988ecf8c75ff340300b83a1faef
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker standard basierend)

Mit [Windows-Containern](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), können Sie Ihre vorhandenen Windows-Anwendungen zum Docker-Images zu konvertieren und mit den gleichen Tools wie der Rest des Docker-Ökosystem bereitstellen.

Um Windows-Container zu verwenden, müssen Sie nur Windows PowerShell-Befehle in die dockerfile-Datei zu schreiben, wie im folgenden Beispiel gezeigt:

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

Windows PowerShell verwenden wir in diesem Fall um ein Windows Server Core-Basis-Image sowie IIS zu installieren.

Auf ähnliche Weise, außerdem können Sie Windows PowerShell-Befehlen einrichten, zusätzliche Komponenten wie die herkömmlichen ASP.NET 4.x und .NET 4.6 oder andere Windows-Software, wie hier gezeigt:

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
[Vorherigen] (Visual-Studio-Tools-für-docker.md) [weiter] (.. /docker-DevOps-Workflow/Index.MD)
