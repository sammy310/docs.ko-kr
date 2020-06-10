---
title: Azure에서 F# 사용
description: F#과 함께 Azure 서비스 사용에 대한 가이드
author: sylvanc
ms.date: 09/22/2016
ms.openlocfilehash: f074ac192f6dedbadf8132430cf27dc5865e6371
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501822"
---
# <a name="using-f-on-azure"></a><span data-ttu-id="822fe-103">Azure에서 F# 사용</span><span class="sxs-lookup"><span data-stu-id="822fe-103">Using F# on Azure</span></span>

<span data-ttu-id="822fe-104">F#은 클라우드 프로그래밍의 뛰어난 언어이며 웹 애플리케이션, 클라우드 서비스, 클라우드 호스티드 마이크로 서비스를 작성하는 데 자주 사용되고 확장 가능한 데이터 처리에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-104">F# is a superb language for cloud programming and is frequently used to write web applications, cloud services, cloud-hosted microservices, and for scalable data processing.</span></span>

<span data-ttu-id="822fe-105">다음 섹션에서 F#과 함께 다양한 Azure 서비스를 사용하는 방법에 대한 리소스를 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-105">In the following sections, you will find resources on how to use a range of Azure services with F#.</span></span>

> [!NOTE]
> <span data-ttu-id="822fe-106">특정 Azure 서비스가 이러한 설명서 집합에 소개되지 않은 경우 해당 서비스에 대한 Azure Functions 또는 .NET 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="822fe-106">If a particular Azure service isn't in this documentation set, please consult either the Azure Functions or .NET documentation for that service.</span></span> <span data-ttu-id="822fe-107">일부 Azure 서비스는 언어의 구애를 받지 않으며 언어와 관련된 설명서를 요구하지 않고 여기에 나열되지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-107">Some Azure services are language-independent and require no language-specific documentation and are not listed here.</span></span>

## <a name="using-azure-virtual-machines-with-f"></a><span data-ttu-id="822fe-108">F\#과 함께 Azure Virtual Machines 사용</span><span class="sxs-lookup"><span data-stu-id="822fe-108">Using Azure Virtual Machines with F\#</span></span>

<span data-ttu-id="822fe-109">Azure는 다양한 VM(가상 머신) 구성을 지원합니다. [Linux 및 Azure Virtual Machines](https://azure.microsoft.com/services/virtual-machines/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="822fe-109">Azure supports a wide range of virtual machine (VM) configurations, see [Linux and Azure Virtual Machines](https://azure.microsoft.com/services/virtual-machines/).</span></span>

<span data-ttu-id="822fe-110">가상 머신에서 F#을 실행하고 컴파일하거나 스크립팅하도록 설치하려면 [Using F# on Linux](https://fsharp.org/use/linux)(Linux에서 F# 사용) 및 [Using F# on Windows](https://fsharp.org/use/windows)(Windows에서 F# 사용)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="822fe-110">To install F# on a virtual machine for execution, compilation and/or scripting see [Using F# on Linux](https://fsharp.org/use/linux) and [Using F# on Windows](https://fsharp.org/use/windows).</span></span>

## <a name="using-azure-functions-with-f"></a><span data-ttu-id="822fe-111">F\#과 함께 Azure Functions 사용</span><span class="sxs-lookup"><span data-stu-id="822fe-111">Using Azure Functions with F\#</span></span>

<span data-ttu-id="822fe-112">[Azure Functions](https://azure.microsoft.com/services/functions/)는 클라우드에서 소량의 코드 또는 "함수"를 쉽게 실행하기 위한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-112">[Azure Functions](https://azure.microsoft.com/services/functions/) is a solution for easily running small pieces of code, or "functions," in the cloud.</span></span> <span data-ttu-id="822fe-113">전체 애플리케이션 또는 이를 실행하는 인프라에 대해 걱정하지 않고, 당면한 문제에 필요한 코드만 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-113">You can write just the code you need for the problem at hand, without worrying about a whole application or the infrastructure to run it.</span></span> <span data-ttu-id="822fe-114">함수는 Azure 스토리지 및 기타 클라우드에 호스트된 리소스의 이벤트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-114">Your functions are connected to events in Azure storage and other cloud-hosted resources.</span></span> <span data-ttu-id="822fe-115">데이터는 함수 인수를 통해 F# 함수로 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-115">Data flows into your F# functions via function arguments.</span></span> <span data-ttu-id="822fe-116">Azure는 필요에 따라 크기를 조정할 수 있으므로 안심하고 선택한 개발 언어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-116">You can use your development language of choice, trusting Azure to scale as needed.</span></span>

<span data-ttu-id="822fe-117">Azure Functions는 F# 코드의 효율적이고 반응적이며 확장 가능한 실행을 통해 F#을 최고의 언어로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-117">Azure Functions support F# as a first-class language with efficient, reactive, scalable execution of F# code.</span></span> <span data-ttu-id="822fe-118">Azure Functions와 함께 F#을 사용하는 방법에 대한 참조 설명서는 [Azure Functions F# 개발자 참조](/azure/azure-functions/functions-reference-fsharp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="822fe-118">See the [Azure Functions F# Developer Reference](/azure/azure-functions/functions-reference-fsharp) for reference documentation on how to use F# with Azure Functions.</span></span>

<span data-ttu-id="822fe-119">Azure Functions 및 F# 사용에 대한 기타 리소스:</span><span class="sxs-lookup"><span data-stu-id="822fe-119">Other resources for using Azure Functions and F#:</span></span>

* [<span data-ttu-id="822fe-120">Suave를 사용하여 F#에서 Azure Functions 확장</span><span class="sxs-lookup"><span data-stu-id="822fe-120">Scale Up Azure Functions in F# Using Suave</span></span>](https://blog.tamizhvendan.in/blog/2016/09/19/scale-up-azure-functions-in-f-number-using-suave/)
* [<span data-ttu-id="822fe-121">F#으로 Azure 함수를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="822fe-121">How to create Azure function in F#</span></span>](https://www.mnie.me/azurefunctions)
* <span data-ttu-id="822fe-122">[Using the Azure Type Provider with Azure Functions](https://compositional-it.com/blog/2017/08-30-using-the-azure-type-provider-with-azure-functions/index.html)(Azure Functions와 함께 Azure 형식 공급자 사용)</span><span class="sxs-lookup"><span data-stu-id="822fe-122">[Using the Azure Type Provider with Azure Functions](https://compositional-it.com/blog/2017/08-30-using-the-azure-type-provider-with-azure-functions/index.html)</span></span>

## <a name="using-azure-storage-with-f"></a><span data-ttu-id="822fe-123">F\#과 함께 Azure Storage 사용</span><span class="sxs-lookup"><span data-stu-id="822fe-123">Using Azure Storage with F\#</span></span>

<span data-ttu-id="822fe-124">Azure Storage는 내구성, 가용성, 확장성을 활용하여 고객의 요구 사항을 충족하는 최신 애플리케이션을 위한 저장소 서비스의 기본 레이어입니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-124">Azure Storage is a base layer of storage services for modern applications that rely on durability, availability, and scalability to meet the needs of customers.</span></span> <span data-ttu-id="822fe-125">F# 프로그램은 다음 문서에 설명된 기술을 사용하여 Azure Storage 서비스를 직접 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-125">F# programs can interact directly with Azure storage services, using the techniques described in the following articles.</span></span>

* [<span data-ttu-id="822fe-126">F#을 사용하여 Azure Blob 스토리지 시작</span><span class="sxs-lookup"><span data-stu-id="822fe-126">Get started with Azure Blob storage using F#</span></span>](blob-storage.md)
* [<span data-ttu-id="822fe-127">F#을 사용하여 Azure File 스토리지 시작</span><span class="sxs-lookup"><span data-stu-id="822fe-127">Get started with Azure File storage using F#</span></span>](file-storage.md)
* [<span data-ttu-id="822fe-128">F#을 사용하여 Azure Queue 스토리지 시작</span><span class="sxs-lookup"><span data-stu-id="822fe-128">Get started with Azure Queue storage using F#</span></span>](queue-storage.md)
* [<span data-ttu-id="822fe-129">F#을 사용하여 Azure Table Storage 시작</span><span class="sxs-lookup"><span data-stu-id="822fe-129">Get started with Azure Table storage using F#</span></span>](table-storage.md)

<span data-ttu-id="822fe-130">명시적 API 호출이 아닌 선언적 구성을 통해 Azure Functions와 함께 Azure Storage를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-130">Azure Storage can also be used in conjunction with Azure Functions through declarative configuration rather than explicit API calls.</span></span> <span data-ttu-id="822fe-131">F# 예제를 포함하는 [Azure Storage를 위한 Azure Functions 트리거 및 바인딩](/azure/azure-functions/functions-bindings-storage)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="822fe-131">See [Azure Functions triggers and bindings for Azure Storage](/azure/azure-functions/functions-bindings-storage) which includes F# examples.</span></span>

## <a name="using-azure-app-service-with-f"></a><span data-ttu-id="822fe-132">F\#과 함께 Azure App Service 사용</span><span class="sxs-lookup"><span data-stu-id="822fe-132">Using Azure App Service with F\#</span></span>

<span data-ttu-id="822fe-133">[Azure App Service](https://azure.microsoft.com/services/app-service/)는 클라우드 또는 온-프레미스 내 어디서든 데이터에 연결되는 강력한 웹 및 모바일 앱을 빌드하는 클라우드 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-133">[Azure App Service](https://azure.microsoft.com/services/app-service/) is a cloud platform to build powerful web and mobile apps that connect to data anywhere, in the cloud or on-premises.</span></span>

* [<span data-ttu-id="822fe-134">F# Azure 웹 API 예제</span><span class="sxs-lookup"><span data-stu-id="822fe-134">F# Azure Web API example</span></span>](https://github.com/fsprojects/azure-webapi-example)
* [<span data-ttu-id="822fe-135">Azure의 웹 애플리케이션에서 F# 호스트</span><span class="sxs-lookup"><span data-stu-id="822fe-135">Hosting F# in a web application on Azure</span></span>](https://github.com/isaacabraham/fsharp-demonstrator)

## <a name="using-apache-spark-with-f-with-azure-hdinsight"></a><span data-ttu-id="822fe-136">F#을 사용한 Apache Spark와 함께 Azure HDInsight 사용</span><span class="sxs-lookup"><span data-stu-id="822fe-136">Using Apache Spark with F# with Azure HDInsight</span></span>

<span data-ttu-id="822fe-137">[Azure HDInsight용 Apache Spark](https://azure.microsoft.com/services/hdinsight/apache-spark/)는 대규모 데이터 분석 애플리케이션을 실행하는 오픈 소스 처리 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-137">[Apache Spark for Azure HDInsight](https://azure.microsoft.com/services/hdinsight/apache-spark/) is an open source processing framework that runs large-scale data analytics applications.</span></span> <span data-ttu-id="822fe-138">Azure는 배포하기에 간단하고 비용 효과적인 Apache Spark를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-138">Azure makes Apache Spark easy and cost effective to deploy.</span></span> <span data-ttu-id="822fe-139">Spark용 .NET API인 [Mobius](https://github.com/Microsoft/Mobius)를 사용하여 F#으로 Spark 애플리케이션을 개발합니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-139">Develop your Spark application in F# using [Mobius](https://github.com/Microsoft/Mobius), a .NET API for Spark.</span></span>

* [<span data-ttu-id="822fe-140">Mobius를 사용하여 F#으로 Spark 앱 구현</span><span class="sxs-lookup"><span data-stu-id="822fe-140">Implementing Spark Apps in F# using Mobius</span></span>](https://github.com/Microsoft/Mobius/blob/master/notes/spark-fsharp-mobius.md)
* [<span data-ttu-id="822fe-141">Mobius를 사용하는 예제 F# Spark 앱</span><span class="sxs-lookup"><span data-stu-id="822fe-141">Example F# Spark Apps using Mobius</span></span>](https://github.com/Microsoft/Mobius/tree/master/examples/fsharp)

## <a name="using-azure-cosmos-db-with-f"></a><span data-ttu-id="822fe-142">F\#과 함께 Azure Cosmos DB 사용</span><span class="sxs-lookup"><span data-stu-id="822fe-142">Using Azure Cosmos DB with F\#</span></span>

<span data-ttu-id="822fe-143">[Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db)는 전역 분산형 고가용성 앱을 위한 NoSQL 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-143">[Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db) is a NoSQL service for highly available, globally distributed apps.</span></span>

<span data-ttu-id="822fe-144">Azure Cosmos DB는 다음과 같은 두 가지 방법으로 F#과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-144">Azure Cosmos DB can be used with F# in two ways:</span></span>

1. <span data-ttu-id="822fe-145">Azure Cosmos DB 컬렉션에 반응하거나 이 컬렉션을 변경하는 F# Azure Functions 생성을 통해.</span><span class="sxs-lookup"><span data-stu-id="822fe-145">Through the creation of F# Azure Functions which react to or cause changes to Azure Cosmos DB collections.</span></span> <span data-ttu-id="822fe-146">[Azure Functions의 Azure Cosmos DB 바인딩](/azure/azure-functions/functions-bindings-cosmosdb)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="822fe-146">See [Azure Cosmos DB bindings for Azure Functions](/azure/azure-functions/functions-bindings-cosmosdb), or</span></span>
2. <span data-ttu-id="822fe-147">[SQL API용 Azure Cosmos DB .NET SDK](/azure/cosmos-db/sql-api-sdk-dotnet)를 사용하여.</span><span class="sxs-lookup"><span data-stu-id="822fe-147">By using the [Azure Cosmos DB .NET SDK for SQL API](/azure/cosmos-db/sql-api-sdk-dotnet).</span></span> <span data-ttu-id="822fe-148">관련 샘플은 C#으로 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-148">The related samples are in C#.</span></span>

## <a name="using-azure-event-hubs-with-f"></a><span data-ttu-id="822fe-149">F\#과 함께 Azure Event Hubs 사용</span><span class="sxs-lookup"><span data-stu-id="822fe-149">Using Azure Event Hubs with F\#</span></span>

<span data-ttu-id="822fe-150">[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/)는 웹 사이트, 앱 및 디바이스에서 클라우드 규모의 원격 분석 수집을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-150">[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/) provide cloud-scale telemetry ingestion from websites, apps, and devices.</span></span>

<span data-ttu-id="822fe-151">Azure Event Hubs는 다음과 같은 두 가지 방법으로 F#과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-151">Azure Event Hubs can be used with F# in two ways:</span></span>

1. <span data-ttu-id="822fe-152">이벤트에 의해 트리거되는 F# Azure Functions의 생성을 통해.</span><span class="sxs-lookup"><span data-stu-id="822fe-152">Through the creation of F# Azure Functions which are triggered by events.</span></span> <span data-ttu-id="822fe-153">[Event Hubs에 대한 Azure Function 트리거](/azure/azure-functions/functions-bindings-event-hubs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="822fe-153">See [Azure Function triggers for Event Hubs](/azure/azure-functions/functions-bindings-event-hubs), or</span></span>
2. <span data-ttu-id="822fe-154">[Azure용 .NET SDK](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted)를 사용하여.</span><span class="sxs-lookup"><span data-stu-id="822fe-154">By using the [.NET SDK for Azure](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted).</span></span> <span data-ttu-id="822fe-155">이러한 예제는 C#으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-155">Note these examples are in C#.</span></span>

## <a name="using-azure-notification-hubs-with-f"></a><span data-ttu-id="822fe-156">F\#과 함께 Azure Notification Hubs 사용</span><span class="sxs-lookup"><span data-stu-id="822fe-156">Using Azure Notification Hubs with F\#</span></span>

<span data-ttu-id="822fe-157">[Azure Notification Hubs](/azure/notification-hubs/)는 백 엔드(클라우드 또는 온-프레미스)에서 임의의 모바일 플랫폼으로 모바일 푸시 알림을 보낼 수 있도록 지원하는 다중 플랫폼의 확장된 푸시 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-157">[Azure Notification Hubs](/azure/notification-hubs/) are multiplatform, scaled-out push infrastructure that enable you to send mobile push notifications from any backend (in the cloud or on-premises) to any mobile platform.</span></span>

<span data-ttu-id="822fe-158">Azure Notification Hubs는 다음과 같은 두 가지 방법으로 F#과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-158">Azure Notification Hubs can be used with F# in two ways:</span></span>

1. <span data-ttu-id="822fe-159">알림 허브로 결과를 보내는 F# Azure Functions 생성을 통해.</span><span class="sxs-lookup"><span data-stu-id="822fe-159">Through the creation of F# Azure Functions which send results to a notification hub.</span></span> <span data-ttu-id="822fe-160">[Notification Hubs에 대한 Azure Function 출력 트리거](/azure/azure-functions/functions-bindings-notification-hubs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="822fe-160">See [Azure Function output triggers for Notification Hubs](/azure/azure-functions/functions-bindings-notification-hubs), or</span></span>
2. <span data-ttu-id="822fe-161">[Azure용 .NET SDK](https://docs.microsoft.com/archive/blogs/azuremobile/push-notifications-using-notification-hub-and-net-backend)를 사용하여.</span><span class="sxs-lookup"><span data-stu-id="822fe-161">By using the [.NET SDK for Azure](https://docs.microsoft.com/archive/blogs/azuremobile/push-notifications-using-notification-hub-and-net-backend).</span></span> <span data-ttu-id="822fe-162">이러한 예제는 C#으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-162">Note these examples are in C#.</span></span>

## <a name="implementing-webhooks-on-azure-with-f"></a><span data-ttu-id="822fe-163">F\#을 사용하여 Azure에서 WebHook 구현</span><span class="sxs-lookup"><span data-stu-id="822fe-163">Implementing WebHooks on Azure with F\#</span></span>

<span data-ttu-id="822fe-164">[Webhook](https://en.wikipedia.org/wiki/Webhook)는 웹 요청을 통해 트리거되는 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-164">A [Webhook](https://en.wikipedia.org/wiki/Webhook) is a callback triggered via a web request.</span></span> <span data-ttu-id="822fe-165">Webhook는 신호 이벤트에 대한 GitHub와 같은 사이트에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-165">Webhooks are used by sites such as GitHub to signal events.</span></span>

<span data-ttu-id="822fe-166">Webhook는 [F#의 Azure Function 및 Webhook 바인딩](/azure/azure-functions/functions-bindings-http-webhook)을 통해 Azure에서 F#으로 구현하고 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-166">Webhooks can be implemented in F# and hosted on Azure via an [Azure Function in F# with a Webhook Binding](/azure/azure-functions/functions-bindings-http-webhook).</span></span>

## <a name="using-webjobs-with-f"></a><span data-ttu-id="822fe-167">F\#과 함께 WebJobs 사용</span><span class="sxs-lookup"><span data-stu-id="822fe-167">Using Webjobs with F\#</span></span>

<span data-ttu-id="822fe-168">[WebJobs](/azure/app-service-web/web-sites-create-web-jobs)는 주문형, 지속형, 예약형의 세 가지 방법으로 App Service 웹앱에서 실행할 수 있는 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-168">[Webjobs](/azure/app-service-web/web-sites-create-web-jobs) are programs you can run in your App Service web app in three ways: on demand, continuously, or on a schedule.</span></span>

[<span data-ttu-id="822fe-169">예제 F# WebJobs</span><span class="sxs-lookup"><span data-stu-id="822fe-169">Example F# Webjob</span></span>](https://github.com/jrr/webjob-project-examples)

## <a name="implementing-timers-on-azure-with-f"></a><span data-ttu-id="822fe-170">F\#을 사용하여 Azure에서 타이머 구현</span><span class="sxs-lookup"><span data-stu-id="822fe-170">Implementing Timers on Azure with F\#</span></span>

<span data-ttu-id="822fe-171">타이머는 일정, 한 번 또는 되풀이에 따라 호출 함수를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-171">Timer triggers call functions based on a schedule, one time or recurring.</span></span>

<span data-ttu-id="822fe-172">타이머는 [F#의 Azure Function 및 타이머 트리거](/azure/azure-functions/functions-bindings-timer)를 통해 Azure에서 F#으로 구현하고 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-172">Timers can be implemented in F# and hosted on Azure via an [Azure Function in F# with a Timer Trigger](/azure/azure-functions/functions-bindings-timer).</span></span>

## <a name="deploying-and-managing-azure-resources-with-f-scripts"></a><span data-ttu-id="822fe-173">F# 스크립트를 통해 Azure 리소스 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="822fe-173">Deploying and Managing Azure Resources with F# Scripts</span></span>

<span data-ttu-id="822fe-174">Azure VM은 Microsoft.Azure.Management 패키지 및 API를 사용하여 프로그래밍 방식으로 배포하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-174">Azure VMs may be programmatically deployed and managed from F# scripts by using the Microsoft.Azure.Management packages and APIs.</span></span> <span data-ttu-id="822fe-175">예를 들어 [.NET용 관리 라이브러리 시작](https://msdn.microsoft.com/library/dn722415.aspx) 및 [Azure Resource Manager 사용](/azure/azure-resource-manager/resource-manager-deployment-model)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="822fe-175">For example, see [Get Started with the Management Libraries for .NET](https://msdn.microsoft.com/library/dn722415.aspx) and [Using Azure Resource Manager](/azure/azure-resource-manager/resource-manager-deployment-model).</span></span>

<span data-ttu-id="822fe-176">마찬가지로, 동일한 구성 요소를 사용하여 F# 스크립트에서 다른 Azure 리소스를 배포하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-176">Likewise, other Azure resources may also be deployed and managed from F# scripts using the same components.</span></span> <span data-ttu-id="822fe-177">예를 들어 F# 스크립트에서 프로그래밍 방식으로 스토리지 계정을 만들고, Azure Cloud Services를 배포하고, Azure Cosmos DB 인스턴스를 만들고, Azure Notifcation Hubs를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-177">For example, you can create storage accounts, deploy Azure Cloud Services, create Azure Cosmos DB instances and manage Azure Notifcation Hubs programmatically from F# scripts.</span></span>

<span data-ttu-id="822fe-178">F# 스크립트를 사용하여 리소스를 배포하고 관리하는 작업은 일반적으로 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="822fe-178">Using F# scripts to deploy and manage resources is not normally necessary.</span></span> <span data-ttu-id="822fe-179">예를 들어 Azure 리소스는 JSON 템플릿 설명에서 직접 배포할 수도 있습니다(매개 변수화할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="822fe-179">For example, Azure resources may also be deployed directly from JSON template descriptions, which can be parameterized.</span></span> <span data-ttu-id="822fe-180">[Azure 퀵 스타트 템플릿](https://azure.microsoft.com/resources/templates/)과 같은 예제를 비롯하여 [Azure Resource Manager 템플릿](/azure/azure-resource-manager/resource-manager-template-best-practices)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="822fe-180">See [Azure Resource Manager Templates](/azure/azure-resource-manager/resource-manager-template-best-practices) including examples such as the [Azure Quickstart Templates](https://azure.microsoft.com/resources/templates/).</span></span>

## <a name="other-resources"></a><span data-ttu-id="822fe-181">기타 리소스</span><span class="sxs-lookup"><span data-stu-id="822fe-181">Other resources</span></span>

* [<span data-ttu-id="822fe-182">모든 Azure 서비스에 대한 전체 설명서</span><span class="sxs-lookup"><span data-stu-id="822fe-182">Full documentation on all Azure services</span></span>](/azure/)
