---
title: "Entwicklungsprozess für Azure"
description: "Innovative Webanwendungen mit ASP.NET Core und Azure Architekt | Entwicklungsprozess für Azure"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: e676c1225f7d11381808040cf101e897e0726ad4
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2017
---
# <a name="development-process-for-azure"></a><span data-ttu-id="b475e-103">Entwicklungsprozess für Azure</span><span class="sxs-lookup"><span data-stu-id="b475e-103">Development process for Azure</span></span>

> <span data-ttu-id="b475e-104">_"Mit der Cloud Einzelpersonen kleine Unternehmen können ihre Finger ausrichten und sofort unternehmenstauglichen Dienste einrichten."_</span><span class="sxs-lookup"><span data-stu-id="b475e-104">_"With the cloud, individuals and small businesses can snap their fingers and instantly set up enterprise-class services."_</span></span>  
> <span data-ttu-id="b475e-105">_-Roy Stephan_</span><span class="sxs-lookup"><span data-stu-id="b475e-105">_- Roy Stephan_</span></span>

 ## <a name="vision"></a><span data-ttu-id="b475e-106">Vision</span><span class="sxs-lookup"><span data-stu-id="b475e-106">Vision</span></span>

> <span data-ttu-id="b475e-107">*Entwickeln Sie ausgereifte ASP .NET Core-Anwendungen die Möglichkeit, die Ihnen gefällt mithilfe des Visual Studio oder die CLI-Dotnet und Visual Studio Code Editor Ihrer Wahl.*</span><span class="sxs-lookup"><span data-stu-id="b475e-107">*Develop well-designed ASP .NET Core applications the way you like, using Visual Studio or the dotnet CLI and Visual Studio Code or your editor of choice.*</span></span>

## <a name="development-environment-for-aspnet-core-apps"></a><span data-ttu-id="b475e-108">Entwicklungsumgebung für apps mit ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b475e-108">Development environment for ASP.NET Core apps</span></span>

### <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="b475e-109">Optionen für Entwicklungstools: IDE oder -Editor</span><span class="sxs-lookup"><span data-stu-id="b475e-109">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="b475e-110">Ob Sie eine vollständige und leistungsfähige IDE oder eine einfache und agile-Editor bevorzugen, hat Microsoft Sie beim Entwickeln von ASP.NET Core Anwendungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="b475e-110">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when developing ASP.NET Core applications.</span></span>

<span data-ttu-id="b475e-111">**Visual Studio-2017.**</span><span class="sxs-lookup"><span data-stu-id="b475e-111">**Visual Studio 2017.**</span></span> <span data-ttu-id="b475e-112">Bei Verwendung von *Visual Studio 2017* können erstellen ASP.NET Core-Anwendungen, solange Sie haben die *.NET Core plattformübergreifende Entwicklung* arbeitsauslastung installiert.</span><span class="sxs-lookup"><span data-stu-id="b475e-112">If you're using *Visual Studio 2017* you can build ASP.NET Core applications as long as you have the *.NET Core cross-platform development* workload installed.</span></span> <span data-ttu-id="b475e-113">Abbildung 10 – 1 zeigt die erforderliche Arbeitslast im Setupdialogfeld 2017 von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b475e-113">Figure 10-1 shows the required workload in the Visual Studio 2017 setup dialog.</span></span>

![](./media/image10-1.png)

<span data-ttu-id="b475e-114">**Abbildung 10 – 1.**</span><span class="sxs-lookup"><span data-stu-id="b475e-114">**Figure 10-1.**</span></span> <span data-ttu-id="b475e-115">Installieren die .NET Core-arbeitsauslastung in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="b475e-115">Installing the .NET Core workload in Visual Studio 2017.</span></span>

[<span data-ttu-id="b475e-116">Visual Studio 2017 herunterladen</span><span class="sxs-lookup"><span data-stu-id="b475e-116">Download Visual Studio 2017</span></span>](https://www.visualstudio.com/downloads/)

<span data-ttu-id="b475e-117">**Visual Studio-Code und Dotnet CLI** (Cross-Platform-Tools für Mac-, Linux- und Windows).</span><span class="sxs-lookup"><span data-stu-id="b475e-117">**Visual Studio Code and dotnet CLI** (Cross-Platform Tools for Mac, Linux and Windows).</span></span> <span data-ttu-id="b475e-118">Wenn Sie einen einfachen und plattformübergreifende-Editor unterstützt Entwicklungssprache bevorzugen, können Sie Microsoft Visual Studio-Code und die Dotnet CLI.</span><span class="sxs-lookup"><span data-stu-id="b475e-118">If you prefer a lightweight and cross-platform editor supporting any development language, you can use Microsoft Visual Studio Code and the dotnet CLI.</span></span> <span data-ttu-id="b475e-119">Diese Produkte bieten eine einfache, aber robuste Erfahrung, die den Entwickler Workflow optimiert.</span><span class="sxs-lookup"><span data-stu-id="b475e-119">These products provide a simple yet robust experience that streamlines the developer workflow.</span></span> <span data-ttu-id="b475e-120">Darüber hinaus unterstützt Visual Studio Code Erweiterungen für C\# und Webentwicklung, die Bereitstellung von Intellisense und Verknüpfung-Aufgaben innerhalb des Editors.</span><span class="sxs-lookup"><span data-stu-id="b475e-120">Additionally, Visual Studio Code supports extensions for C\# and web development, providing intellisense and shortcut-tasks within the editor.</span></span>

[<span data-ttu-id="b475e-121">Die .NET Core SDK herunterladen</span><span class="sxs-lookup"><span data-stu-id="b475e-121">Download the .NET Core SDK</span></span>](https://www.microsoft.com/net/download/core)

[<span data-ttu-id="b475e-122">Herunterladen der Visual Studio-Code</span><span class="sxs-lookup"><span data-stu-id="b475e-122">Download Visual Studio Code</span></span>](https://code.visualstudio.com/download)



## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a><span data-ttu-id="b475e-123">Entwicklungsworkflow für Azure gehosteten ASP.NET Core-apps</span><span class="sxs-lookup"><span data-stu-id="b475e-123">Development workflow for Azure-hosted ASP.NET Core apps</span></span>

<span data-ttu-id="b475e-124">Lebenszyklus der Anwendungsentwicklung beginnt bei jeder Entwickler-Computer, codieren die app ihre bevorzugte Programmiersprache und lokal testen.</span><span class="sxs-lookup"><span data-stu-id="b475e-124">The application development lifecycle starts from each developer's machine, coding the app using their preferred language and testing it locally.</span></span> <span data-ttu-id="b475e-125">Entwickler können ihre bevorzugte Quellcodeverwaltungssystem und fortlaufende Integration (CI) und/oder Continuous Delivery/Bereitstellung (CD) mit einem Build-Server konfigurieren können oder basierend auf den integrierten Azure-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="b475e-125">Developers may choose their preferred source control system and can configure Continuous Integration (CI) and/or Continuous Delivery/Deployment (CD) using a build server or based on built-in Azure features.</span></span>

<span data-ttu-id="b475e-126">Zum Einstieg in eine ASP.NET Core-Anwendung, die mit der CI-CD zu entwickeln, können Sie die Visual Studio Team Services oder Ihrer Organisation verwenden Team Foundation Server (TFS) besitzen.</span><span class="sxs-lookup"><span data-stu-id="b475e-126">To get started with developing an ASP.NET Core application using CI/CD, you can use Visual Studio Team Services or your organization's own Team Foundation Server (TFS).</span></span>

### <a name="initial-setup"></a><span data-ttu-id="b475e-127">Anfangssetup</span><span class="sxs-lookup"><span data-stu-id="b475e-127">Initial Setup</span></span>

<span data-ttu-id="b475e-128">Um einer releasepipeline für Ihre app zu erstellen, müssen Sie den Anwendungscode in der quellcodeverwaltung haben.</span><span class="sxs-lookup"><span data-stu-id="b475e-128">To create a release pipeline for your app, you need to have your application code in source control.</span></span> <span data-ttu-id="b475e-129">Richten Sie ein lokales Repository, und verbinden Sie ihn in einem Remoterepository in einem Teamprojekt.</span><span class="sxs-lookup"><span data-stu-id="b475e-129">Set up a local repository and connect it to a remote repository in a team project.</span></span> <span data-ttu-id="b475e-130">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="b475e-130">Follow these instructions:</span></span>

-   <span data-ttu-id="b475e-131">[Freigeben von Code mit Git als auch Visual Studio](https://www.visualstudio.com/docs/git/share-your-code-in-git-vs) oder</span><span class="sxs-lookup"><span data-stu-id="b475e-131">[Share your code with Git and Visual Studio](https://www.visualstudio.com/docs/git/share-your-code-in-git-vs) or</span></span>

-   [<span data-ttu-id="b475e-132">Freigeben von Code in TFVC und Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b475e-132">Share your code with TFVC and Visual Studio</span></span>](https://www.visualstudio.com/docs/tfvc/share-your-code-in-tfvc-vs)

<span data-ttu-id="b475e-133">Erstellen Sie ein Azure App Service, in dem Sie Ihre Anwendung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b475e-133">Create an Azure App Service where you'll deploy your application.</span></span> <span data-ttu-id="b475e-134">Erstellen Sie eine Web-App, gehen Sie im Azure-Portal auf dem Blatt "App-Dienste".</span><span class="sxs-lookup"><span data-stu-id="b475e-134">Create a Web App by going to the App Services blade on the Azure portal.</span></span> <span data-ttu-id="b475e-135">Klicken Sie auf "+" hinzufügen, wählen Sie die Web-App-Vorlage, klicken Sie auf erstellen, und geben Sie einen Namen und andere Details.</span><span class="sxs-lookup"><span data-stu-id="b475e-135">Click +Add, select the Web App template, click Create, and provide a name and other details.</span></span> <span data-ttu-id="b475e-136">Die Web-app von {Name} zugegriffen werden. azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="b475e-136">The web app will be accessible from {name}.azurewebsites.net.</span></span>

![AzureWebApp](./media/image10-2.png)

<span data-ttu-id="b475e-138">**Abbildung 10 – 2.**</span><span class="sxs-lookup"><span data-stu-id="b475e-138">**Figure 10-2.**</span></span> <span data-ttu-id="b475e-139">Erstellen eine neue Azure App Service Web-App im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="b475e-139">Creating a new Azure App Service Web App in the Azure Portal.</span></span>

<span data-ttu-id="b475e-140">CI-Build-Prozess führt einen automatischen Buildvorgang aus, wenn Sie neuer Code an das Projekt Quellcodeverwaltungs-Repository übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="b475e-140">Your CI build process will perform an automated build whenever new code is committed to the project's source control repository.</span></span> <span data-ttu-id="b475e-141">Dadurch erhalten Sie unmittelbar Feedback, in dem der Code erstellt (und automatisierte Tests im Idealfall übergibt) und potenziell bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b475e-141">This gives you immediate feedback that the code builds (and, ideally, passes automated tests) and can potentially be deployed.</span></span> <span data-ttu-id="b475e-142">Dieser CI-Build erzeugt eine Web Artefakt Paket bereitstellen und veröffentlichen Sie es für die Nutzung vom CD-Prozess.</span><span class="sxs-lookup"><span data-stu-id="b475e-142">This CI build will produce a web deploy package artifact and publish it for consumption by your CD process.</span></span>

[<span data-ttu-id="b475e-143">Definieren des Buildprozesses CI</span><span class="sxs-lookup"><span data-stu-id="b475e-143">Define your CI build process</span></span>](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#ci)

<span data-ttu-id="b475e-144">Achten Sie darauf, dass Sie die fortlaufende Integration zu aktivieren, damit das System einen Build in die Warteschlange wird immer eine Person in Ihrem Team führt einen Commit für neuen Code.</span><span class="sxs-lookup"><span data-stu-id="b475e-144">Be sure to enable continuous integration so the system will queue a build whenever someone on your team commits new code.</span></span> <span data-ttu-id="b475e-145">Testen Sie den Build, und stellen Sie sicher, dass sie eine Web erzeugt Paket als eines seiner Elemente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b475e-145">Test the build and verify that it is producing a web deploy package as one of its artifacts.</span></span>

<span data-ttu-id="b475e-146">Wenn ein Build erfolgreich ist, stellt der CD-Prozess die Ergebnisse der CI-Build für Ihre Azure-Web-app bereit.</span><span class="sxs-lookup"><span data-stu-id="b475e-146">When a build succeeds, your CD process will deploy the results of your CI build to your Azure web app.</span></span> <span data-ttu-id="b475e-147">Um dies zu konfigurieren, erstellen und konfigurieren Sie eine *Version*, die Bereitstellung in Ihren Azure App Service.</span><span class="sxs-lookup"><span data-stu-id="b475e-147">To configure this, you create and configure a *Release*, which will deploy to your Azure App Service.</span></span>

[<span data-ttu-id="b475e-148">Definieren Sie den versionsprozess CD</span><span class="sxs-lookup"><span data-stu-id="b475e-148">Define your CD release process</span></span>](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#cd)

<span data-ttu-id="b475e-149">Sobald die CI-CD-Pipeline konfiguriert ist, können Sie einfach Updates auf Ihre Web-app und übernehmen sie zur quellcodeverwaltung, die sie bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="b475e-149">Once your CI/CD pipeline is configured, you can simply make updates to your web app and commit them to source control to have them deployed.</span></span>

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a><span data-ttu-id="b475e-150">Workflow für die Entwicklung von Azure gehosteten ASP.NET Core-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b475e-150">Workflow for developing Azure-hosted ASP.NET Core applications</span></span>

<span data-ttu-id="b475e-151">Nachdem Sie Ihre Azure-Konto und den CI-CD-Prozess konfiguriert haben, ist die Entwicklung von Azure gehosteten ASP.NET Core-Anwendungen einfach.</span><span class="sxs-lookup"><span data-stu-id="b475e-151">Once you have configured your Azure account and your CI/CD process, developing Azure-hosted ASP.NET Core applications is simple.</span></span> <span data-ttu-id="b475e-152">Im folgenden sind die grundlegenden Schritte, die Sie normalerweise, beim Erstellen einer ASP.NET Core-app in Azure App Service als eine Web-App gehostet wird ausführen, wie in Abbildung 10 – 3 veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b475e-152">The following are the basic steps you usually take when building an ASP.NET Core app, hosted in Azure App Service as a Web App, as illustrated in Figure 10-3.</span></span>

![EndToEndDevDeployWorkflow](./media/image10-3.png)

<span data-ttu-id="b475e-154">**Abbildung 10 – 3.**</span><span class="sxs-lookup"><span data-stu-id="b475e-154">**Figure 10-3.**</span></span> <span data-ttu-id="b475e-155">Schrittweise Workflow zum Erstellen von ASP.NET Core-apps und das Hosten dieser in Azure</span><span class="sxs-lookup"><span data-stu-id="b475e-155">Step-by-step workflow for building ASP.NET Core apps and hosting them in Azure</span></span>

#### <a name="step-1-local-dev-environment-inner-loop"></a><span data-ttu-id="b475e-156">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="b475e-156">Step 1.</span></span> <span data-ttu-id="b475e-157">Lokale Dev Umgebung innere Schleife</span><span class="sxs-lookup"><span data-stu-id="b475e-157">Local Dev Environment Inner Loop</span></span>

<span data-ttu-id="b475e-158">Entwickeln Ihrer Anwendung ASP.NET Core zur Bereitstellung in Azure unterscheidet sich nicht von andernfalls Entwickeln Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b475e-158">Developing your ASP.NET Core application for deployment to Azure is no different from developing your application otherwise.</span></span> <span data-ttu-id="b475e-159">Verwenden Sie die lokalen Entwicklungs-Umgebung aus, der Sie mit, vertraut sind, ob das Visual Studio-2017 oder Dotnet-CLI und Visual Studio-Code oder Ihrem bevorzugten Text-Editor ist.</span><span class="sxs-lookup"><span data-stu-id="b475e-159">Use the local development environment you're comfortable with, whether that's Visual Studio 2017 or the dotnet CLI and Visual Studio Code or your preferred editor.</span></span> <span data-ttu-id="b475e-160">Sie können Code schreiben, ausführen und Debuggen die Änderungen, Ausführen von automatisierten Tests und lokalen Commits zur quellcodeverwaltung stellen, bis Sie die Änderungen per Push auf Ihre freigegebenen Quellcodeverwaltungs-Repository übertragen möchten.</span><span class="sxs-lookup"><span data-stu-id="b475e-160">You can write code, run and debug your changes, run automated tests, and make local commits to source control until you're ready to push your changes to your shared source control repository.</span></span>

#### <a name="step-2-application-code-repository"></a><span data-ttu-id="b475e-161">Schritt 2</span><span class="sxs-lookup"><span data-stu-id="b475e-161">Step 2.</span></span> <span data-ttu-id="b475e-162">Anwendung Code Repository</span><span class="sxs-lookup"><span data-stu-id="b475e-162">Application Code Repository</span></span>

<span data-ttu-id="b475e-163">Wenn Sie zur Freigabe des Codes mit Ihrem Team bereit sind, sollten Sie Ihre Änderungen aus Ihrem lokalen Quellrepository zu freigegebenen Quellrepository Ihres Teams per Push übertragen.</span><span class="sxs-lookup"><span data-stu-id="b475e-163">Whenever you're ready to share your code with your team, you should push your changes from your local source repository to your team's shared source repository.</span></span> <span data-ttu-id="b475e-164">Wenn Sie in einer benutzerdefinierten Verzweigung gearbeitet haben, in der Regel dieser Schritt umfasst das Zusammenführen von Code in eine freigegebene Verzweigung (z. B. mithilfe von einer [Pull-Anforderung](https://www.visualstudio.com/docs/git/pull-requests)).</span><span class="sxs-lookup"><span data-stu-id="b475e-164">If you've been working in a custom branch, this step usually involves merging your code into a shared branch (perhaps by means of a [pull request](https://www.visualstudio.com/docs/git/pull-requests)).</span></span>

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a><span data-ttu-id="b475e-165">Schritt 3</span><span class="sxs-lookup"><span data-stu-id="b475e-165">Step 3.</span></span> <span data-ttu-id="b475e-166">Build-Server: Fortlaufende Integration.</span><span class="sxs-lookup"><span data-stu-id="b475e-166">Build Server: Continuous Integration.</span></span> <span data-ttu-id="b475e-167">Build, Test-Paket</span><span class="sxs-lookup"><span data-stu-id="b475e-167">Build, Test, Package</span></span>

<span data-ttu-id="b475e-168">Ein neuer Build wird auf dem Buildserver ausgelöst, wenn ein neuer Commit an die freigegebene Anwendung Code Repository vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="b475e-168">A new build is triggered on the build server whenever a new commit is made to the shared application code repository.</span></span> <span data-ttu-id="b475e-169">Als Teil der CI-Prozess sollte dieser Build vollständig kompilieren Sie die Anwendung und Ausführen von automatisierten Tests, um sicherzustellen, dass alles wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b475e-169">As part of the CI process, this build should fully compile the application and run automated tests to confirm everything is working as expected.</span></span> <span data-ttu-id="b475e-170">Das Endergebnis der CI-Prozess sollte eine gepackte Version der Web-app, für die Bereitstellung bereit.</span><span class="sxs-lookup"><span data-stu-id="b475e-170">The end result of the CI process should be a packaged version of the web app, ready for deployment.</span></span>

#### <a name="step-4-build-server-continuous-delivery"></a><span data-ttu-id="b475e-171">Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="b475e-171">Step 4.</span></span> <span data-ttu-id="b475e-172">Build-Server: Continuous Delivery</span><span class="sxs-lookup"><span data-stu-id="b475e-172">Build Server: Continuous Delivery</span></span>

<span data-ttu-id="b475e-173">Einmal einen Build als erfolgreich, das CD-Prozess die Build-Elemente, die erzeugt übernehmen.</span><span class="sxs-lookup"><span data-stu-id="b475e-173">Once a build as succeeded, the CD process will pick up the build artifacts produced.</span></span> <span data-ttu-id="b475e-174">Dazu gehören eine Web deploy-Paket.</span><span class="sxs-lookup"><span data-stu-id="b475e-174">This will include a web deploy package.</span></span> <span data-ttu-id="b475e-175">Der Build-Server stellt dieses Paket für Azure App Service, und Ersetzen Sie dabei alle vorhandenen Dienst mit der neu erstellten bereit.</span><span class="sxs-lookup"><span data-stu-id="b475e-175">The build server will deploy this package to Azure App Service, replacing any existing service with the newly created one.</span></span> <span data-ttu-id="b475e-176">In der Regel wird dieser Schritt eine Stagingumgebung ausgerichtet ist, aber einige Anwendungen, die direkt für die Produktion durch einen CD-Prozess bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b475e-176">Typically this step targets a staging environment, but some applications deploy directly to production through a CD process.</span></span>

#### <a name="step-5-azure-app-service-web-app"></a><span data-ttu-id="b475e-177">Schritt 5.</span><span class="sxs-lookup"><span data-stu-id="b475e-177">Step 5.</span></span> <span data-ttu-id="b475e-178">Azure App Service.</span><span class="sxs-lookup"><span data-stu-id="b475e-178">Azure App Service.</span></span> <span data-ttu-id="b475e-179">Web-App.</span><span class="sxs-lookup"><span data-stu-id="b475e-179">Web App.</span></span>

<span data-ttu-id="b475e-180">Nach der Bereitstellung wird die ASP.NET Core-Anwendung im Kontext einer Azure App Service-Web-App ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b475e-180">Once deployed, the ASP.NET Core application runs within the context of an Azure App Service Web App.</span></span> <span data-ttu-id="b475e-181">Diese Web-App können überwacht werden und weiter konfiguriert mithilfe des Azure-Portals.</span><span class="sxs-lookup"><span data-stu-id="b475e-181">This Web App can be monitored and further configured using the Azure Portal.</span></span>

#### <a name="step-6-production-monitoring-and-diagnostics"></a><span data-ttu-id="b475e-182">Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="b475e-182">Step 6.</span></span> <span data-ttu-id="b475e-183">Produktion Überwachung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="b475e-183">Production Monitoring and Diagnostics</span></span>

<span data-ttu-id="b475e-184">Während der Web-App ausgeführt wird, können Sie die Integrität der Anwendung überwachen und Sammeln von Diagnose- und Verhalten von Benutzerdaten.</span><span class="sxs-lookup"><span data-stu-id="b475e-184">While the Web App is running, you can monitor the health of the application and collect diagnostics and user behavior data.</span></span> <span data-ttu-id="b475e-185">Application Insights in Visual Studio enthalten ist, und bietet automatische Instrumentation für ASP.NET-Apps.</span><span class="sxs-lookup"><span data-stu-id="b475e-185">Application Insights is included in Visual Studio, and offers automatic instrumentation for ASP.NET apps.</span></span> <span data-ttu-id="b475e-186">Sie können Sie Informationen zur Nutzung, Ausnahmen, Anforderungen, Leistung und Protokolle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b475e-186">It can provide you with information on usage, exceptions, requests, performance, and logs.</span></span>

## <a name="references"></a><span data-ttu-id="b475e-187">Verweise</span><span class="sxs-lookup"><span data-stu-id="b475e-187">References</span></span>

<span data-ttu-id="b475e-188">**Erstellen und Bereitstellen der ASP.NET Core-App in Azure**</span><span class="sxs-lookup"><span data-stu-id="b475e-188">**Build and Deploy Your ASP.NET Core App to Azure**</span></span>  
<span data-ttu-id="b475e-189"><https://www.VisualStudio.com/docs/Build/Apps/ASPNET/aspnetcore-to-Azure></span><span class="sxs-lookup"><span data-stu-id="b475e-189"><https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b475e-190">[Vorherigen] (Test-asp-net-core-mvc-apps.md) [weiter] (Azure-hosting-recommendations-for-asp-net-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="b475e-190">[Previous] (test-asp-net-core-mvc-apps.md) [Next] (azure-hosting-recommendations-for-asp-net-web-apps.md)</span></span>