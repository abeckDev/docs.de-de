---
title: Beim Bereitstellen von Windows-Container auf Azure-VMs (IaaS-Cloud)
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Beim Bereitstellen von Windows-Container auf Azure-VMs (IaaS-Cloud)"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 37a37f91bb910004128c96511f585bea03a51d3a
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Beim Bereitstellen von Windows-Container auf Azure-VMs (IaaS-Cloud)

Wenn Ihre Organisation Azure-VMs verwendet, auch wenn Sie auch Windows-Container verwendet werden, werden Sie immer noch Umgang mit IaaS. Das bedeutet, Umgang mit infrastrukturvorgängen VM Betriebssystempatches und Komplexität der Infrastruktur für hoch skalierbare Anwendungen, wenn Sie mehrere virtuelle Computer in einer Load balanced Infrastruktur bereitstellen müssen. Die wichtigsten Szenarien für die Verwendung von Windows-Containern in einer Azure-VM werden:

-   **Entwicklungs-/testumgebung**: ein virtueller Computer in der Cloud ist ideal für Entwicklung und Tests in der Cloud. Sie können schnell erstellen, oder Beenden der Umgebung je nach Ihren Anforderungen.

-   **Kleine und mittlere Skalierbarkeit muss**: In Szenarien, in denen Sie möglicherweise nur einige der virtuellen Computer für Ihre produktionsumgebung, verwalten eine kleine Anzahl von virtuellen Computern möglicherweise kostengünstige Entwicklung von bis zu komplexeren PaaS-Umgebungen, z. B. Orchestrators verschoben werden kann.

-   **Produktionsumgebung mit vorhandenen Bereitstellungstools**: Sie können aus einer lokalen Umgebung in der Sie in den Tools zu komplexe Bereitstellungen auf virtuellen Computern oder bare-Metal-Servern (z. B. Puppet oder ähnliche Tools) investiert haben gebracht werden sollen. Um mit minimalen codeänderungen zur Produktion Umgebung Bereitstellungsverfahren in der Cloud zu verschieben, können Sie weiterhin diese Tools verwenden, um auf Azure-VMs bereitstellen. Allerdings sollten Sie Windows-Container als Einheit der Bereitstellung zu verwenden, um die Bereitstellung verbessern.

>[!div class="step-by-step"]
[Zurück](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Weiter](when-to-deploy-windows-containers-to-service-fabric.md)
