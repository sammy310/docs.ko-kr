---
title: Azure에서 F# 사용
description: F#과 함께 Azure 서비스 사용에 대한 가이드
author: sylvanc
ms.date: 07/29/2020
ms.openlocfilehash: 0f516b8a3b4fd60eea8facad83a440e33ffd521c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548425"
---
# <a name="using-f-on-azure"></a><span data-ttu-id="6ecfb-103">Azure에서 F# 사용</span><span class="sxs-lookup"><span data-stu-id="6ecfb-103">Using F# on Azure</span></span>

<span data-ttu-id="6ecfb-104">F#은 클라우드 프로그래밍의 뛰어난 언어이며 웹 애플리케이션, 클라우드 서비스, 클라우드 호스티드 마이크로 서비스를 작성하는 데 자주 사용되고 확장 가능한 데이터 처리에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-104">F# is a superb language for cloud programming and is frequently used to write web applications, cloud services, cloud-hosted microservices, and for scalable data processing.</span></span>

<span data-ttu-id="6ecfb-105">다음 섹션에서 F#과 함께 다양한 Azure 서비스를 사용하는 방법에 대한 리소스를 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-105">In the following sections, you will find resources on how to use a range of Azure services with F#.</span></span>

> [!NOTE]
> <span data-ttu-id="6ecfb-106">특정 Azure 서비스가 이러한 설명서 집합에 소개되지 않은 경우 해당 서비스에 대한 Azure Functions 또는 .NET 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-106">If a particular Azure service isn't in this documentation set, please consult either the Azure Functions or .NET documentation for that service.</span></span> <span data-ttu-id="6ecfb-107">일부 Azure 서비스는 언어의 구애를 받지 않으며 언어와 관련된 설명서를 요구하지 않고 여기에 나열되지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-107">Some Azure services are language-independent and require no language-specific documentation and are not listed here.</span></span>

## <a name="using-azure-virtual-machines-with-f"></a><span data-ttu-id="6ecfb-108">F\#과 함께 Azure Virtual Machines 사용</span><span class="sxs-lookup"><span data-stu-id="6ecfb-108">Using Azure Virtual Machines with F\#</span></span>

<span data-ttu-id="6ecfb-109">Azure는 다양한 VM(가상 머신) 구성을 지원합니다. [Linux 및 Azure Virtual Machines](https://azure.microsoft.com/services/virtual-machines/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-109">Azure supports a wide range of virtual machine (VM) configurations, see [Linux and Azure Virtual Machines](https://azure.microsoft.com/services/virtual-machines/).</span></span>

<span data-ttu-id="6ecfb-110">가상 머신에서 F#을 실행하고 컴파일하거나 스크립팅하도록 설치하려면 [Using F# on Linux](https://fsharp.org/use/linux)(Linux에서 F# 사용) 및 [Using F# on Windows](https://fsharp.org/use/windows)(Windows에서 F# 사용)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-110">To install F# on a virtual machine for execution, compilation and/or scripting see [Using F# on Linux](https://fsharp.org/use/linux) and [Using F# on Windows](https://fsharp.org/use/windows).</span></span>

## <a name="using-azure-functions-with-f"></a><span data-ttu-id="6ecfb-111">F\#과 함께 Azure Functions 사용</span><span class="sxs-lookup"><span data-stu-id="6ecfb-111">Using Azure Functions with F\#</span></span>

<span data-ttu-id="6ecfb-112">[Azure Functions](https://azure.microsoft.com/services/functions/)는 클라우드에서 소량의 코드 또는 "함수"를 쉽게 실행하기 위한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-112">[Azure Functions](https://azure.microsoft.com/services/functions/) is a solution for easily running small pieces of code, or "functions," in the cloud.</span></span> <span data-ttu-id="6ecfb-113">전체 애플리케이션 또는 이를 실행하는 인프라에 대해 걱정하지 않고, 당면한 문제에 필요한 코드만 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-113">You can write just the code you need for the problem at hand, without worrying about a whole application or the infrastructure to run it.</span></span> <span data-ttu-id="6ecfb-114">함수는 Azure 스토리지 및 기타 클라우드에 호스트된 리소스의 이벤트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-114">Your functions are connected to events in Azure storage and other cloud-hosted resources.</span></span> <span data-ttu-id="6ecfb-115">데이터는 함수 인수를 통해 F# 함수로 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-115">Data flows into your F# functions via function arguments.</span></span> <span data-ttu-id="6ecfb-116">Azure는 필요에 따라 크기를 조정할 수 있으므로 안심하고 선택한 개발 언어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-116">You can use your development language of choice, trusting Azure to scale as needed.</span></span>

<span data-ttu-id="6ecfb-117">Azure Functions는 F# 코드의 효율적이고 반응적이며 확장 가능한 실행을 통해 F#을 최고의 언어로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-117">Azure Functions support F# as a first-class language with efficient, reactive, scalable execution of F# code.</span></span> <span data-ttu-id="6ecfb-118">Azure Functions와 함께 F#을 사용하는 방법에 대한 참조 설명서는 [Azure Functions F# 개발자 참조](/azure/azure-functions/functions-reference-fsharp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-118">See the [Azure Functions F# Developer Reference](/azure/azure-functions/functions-reference-fsharp) for reference documentation on how to use F# with Azure Functions.</span></span>

<span data-ttu-id="6ecfb-119">Azure Functions 및 F# 사용에 대한 기타 리소스:</span><span class="sxs-lookup"><span data-stu-id="6ecfb-119">Other resources for using Azure Functions and F#:</span></span>

* [<span data-ttu-id="6ecfb-120">Suave를 사용하여 F#에서 Azure Functions 확장</span><span class="sxs-lookup"><span data-stu-id="6ecfb-120">Scale Up Azure Functions in F# Using Suave</span></span>](https://blog.tamizhvendan.in/blog/2016/09/19/scale-up-azure-functions-in-f-number-using-suave/)
* [<span data-ttu-id="6ecfb-121">F#으로 Azure 함수를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="6ecfb-121">How to create Azure function in F#</span></span>](https://www.mnie.me/azurefunctions)
* <span data-ttu-id="6ecfb-122">[Using the Azure Type Provider with Azure Functions](https://compositional-it.com/blog/2017/08-30-using-the-azure-type-provider-with-azure-functions/index.html)(Azure Functions와 함께 Azure 형식 공급자 사용)</span><span class="sxs-lookup"><span data-stu-id="6ecfb-122">[Using the Azure Type Provider with Azure Functions](https://compositional-it.com/blog/2017/08-30-using-the-azure-type-provider-with-azure-functions/index.html)</span></span>

## <a name="using-azure-storage-with-f"></a><span data-ttu-id="6ecfb-123">F\#과 함께 Azure Storage 사용</span><span class="sxs-lookup"><span data-stu-id="6ecfb-123">Using Azure Storage with F\#</span></span>

<span data-ttu-id="6ecfb-124">Azure Storage는 내구성, 가용성, 확장성을 활용하여 고객의 요구 사항을 충족하는 최신 애플리케이션을 위한 저장소 서비스의 기본 레이어입니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-124">Azure Storage is a base layer of storage services for modern applications that rely on durability, availability, and scalability to meet the needs of customers.</span></span> <span data-ttu-id="6ecfb-125">F# 프로그램은 다음 문서에 설명된 기술을 사용하여 Azure Storage 서비스를 직접 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-125">F# programs can interact directly with Azure storage services, using the techniques described in the following articles.</span></span>

* [<span data-ttu-id="6ecfb-126">F#을 사용하여 Azure Blob 스토리지 시작</span><span class="sxs-lookup"><span data-stu-id="6ecfb-126">Get started with Azure Blob storage using F#</span></span>](blob-storage.md)
* [<span data-ttu-id="6ecfb-127">F#을 사용하여 Azure File 스토리지 시작</span><span class="sxs-lookup"><span data-stu-id="6ecfb-127">Get started with Azure File storage using F#</span></span>](file-storage.md)
* [<span data-ttu-id="6ecfb-128">F#을 사용하여 Azure Queue 스토리지 시작</span><span class="sxs-lookup"><span data-stu-id="6ecfb-128">Get started with Azure Queue storage using F#</span></span>](queue-storage.md)
* [<span data-ttu-id="6ecfb-129">F#을 사용하여 Azure Table Storage 시작</span><span class="sxs-lookup"><span data-stu-id="6ecfb-129">Get started with Azure Table storage using F#</span></span>](table-storage.md)

<span data-ttu-id="6ecfb-130">명시적 API 호출이 아닌 선언적 구성을 통해 Azure Functions와 함께 Azure Storage를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-130">Azure Storage can also be used in conjunction with Azure Functions through declarative configuration rather than explicit API calls.</span></span> <span data-ttu-id="6ecfb-131">F# 예제를 포함하는 [Azure Storage를 위한 Azure Functions 트리거 및 바인딩](/azure/azure-functions/functions-bindings-storage)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-131">See [Azure Functions triggers and bindings for Azure Storage](/azure/azure-functions/functions-bindings-storage) which includes F# examples.</span></span>

## <a name="using-azure-app-service-with-f"></a><span data-ttu-id="6ecfb-132">F\#과 함께 Azure App Service 사용</span><span class="sxs-lookup"><span data-stu-id="6ecfb-132">Using Azure App Service with F\#</span></span>

<span data-ttu-id="6ecfb-133">[Azure App Service](https://azure.microsoft.com/services/app-service/)는 클라우드 또는 온-프레미스 내 어디서든 데이터에 연결되는 강력한 웹 및 모바일 앱을 빌드하는 클라우드 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-133">[Azure App Service](https://azure.microsoft.com/services/app-service/) is a cloud platform to build powerful web and mobile apps that connect to data anywhere, in the cloud or on-premises.</span></span>

* [<span data-ttu-id="6ecfb-134">F# Azure 웹 API 예제</span><span class="sxs-lookup"><span data-stu-id="6ecfb-134">F# Azure Web API example</span></span>](https://github.com/fsprojects/azure-webapi-example)
* [<span data-ttu-id="6ecfb-135">Azure의 웹 애플리케이션에서 F# 호스트</span><span class="sxs-lookup"><span data-stu-id="6ecfb-135">Hosting F# in a web application on Azure</span></span>](https://github.com/isaacabraham/fsharp-demonstrator)

## <a name="using-apache-spark-with-f-on-azure-hdinsight-or-azure-databricks"></a><span data-ttu-id="6ecfb-136">Azure HDInsight 또는 Azure Databricks에서 F#과 함께 Apache Spark 사용</span><span class="sxs-lookup"><span data-stu-id="6ecfb-136">Using Apache Spark with F# on Azure HDInsight or Azure Databricks</span></span>

<span data-ttu-id="6ecfb-137">[Azure HDInsight용 Apache Spark](/azure/hdinsight/spark/apache-spark-overview)는 대규모 데이터 분석 애플리케이션을 실행하는 오픈 소스 처리 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-137">[Apache Spark for Azure HDInsight](/azure/hdinsight/spark/apache-spark-overview) is an open source processing framework that runs large-scale data analytics applications.</span></span> <span data-ttu-id="6ecfb-138">[Azure Databricks](/azure/databricks/scenarios/what-is-azure-databricks)는 Microsoft Azure Cloud Services 플랫폼에 대해 최적화된 Apache Spark 기반 분석 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-138">[Azure Databricks](/azure/databricks/scenarios/what-is-azure-databricks) is an Apache Spark-based analytics platform optimized for the Microsoft Azure cloud services platform.</span></span> <span data-ttu-id="6ecfb-139">Azure는 배포하기에 간단하고 비용 효과적인 Apache Spark를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-139">Azure makes Apache Spark easy and cost effective to deploy.</span></span> <span data-ttu-id="6ecfb-140">Apache Spark용 .NET 바인딩 세트인 [.NET for Apache Spark](../../spark/what-is-apache-spark-dotnet.md)를 사용하여 F#으로 Spark 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-140">Develop your Spark application in F# using [.NET for Apache Spark](../../spark/what-is-apache-spark-dotnet.md), a set of .NET bindings for Apache Spark.</span></span>

* [<span data-ttu-id="6ecfb-141">.NET for Apache Spark F# 샘플</span><span class="sxs-lookup"><span data-stu-id="6ecfb-141">.NET for Apache Spark F# samples</span></span>](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.FSharp.Examples)
* [<span data-ttu-id="6ecfb-142">Azure HDInsight에서 .NET Interactive Jupyter Notebook 설치</span><span class="sxs-lookup"><span data-stu-id="6ecfb-142">Install .NET Interactive Jupyter notebooks in Azure HDInsight</span></span>](../../spark/how-to-guides/hdinsight-notebook-installation.md)
* [<span data-ttu-id="6ecfb-143">Azure HDInsight에 Apache Spark 작업 제출</span><span class="sxs-lookup"><span data-stu-id="6ecfb-143">Submit Apache Spark jobs to Azure HDInsight</span></span>](../../spark/how-to-guides/hdinsight-deploy-methods.md)
* [<span data-ttu-id="6ecfb-144">Azure Databricks에 Apache Spark 작업 제출</span><span class="sxs-lookup"><span data-stu-id="6ecfb-144">Submit Apache Spark jobs to Azure Databricks</span></span>](../../spark/how-to-guides/databricks-deploy-methods.md)

## <a name="using-azure-cosmos-db-with-f"></a><span data-ttu-id="6ecfb-145">F\#과 함께 Azure Cosmos DB 사용</span><span class="sxs-lookup"><span data-stu-id="6ecfb-145">Using Azure Cosmos DB with F\#</span></span>

<span data-ttu-id="6ecfb-146">[Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db)는 전역 분산형 고가용성 앱을 위한 NoSQL 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-146">[Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db) is a NoSQL service for highly available, globally distributed apps.</span></span>

<span data-ttu-id="6ecfb-147">Azure Cosmos DB는 다음과 같은 두 가지 방법으로 F#과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-147">Azure Cosmos DB can be used with F# in two ways:</span></span>

1. <span data-ttu-id="6ecfb-148">Azure Cosmos DB 컬렉션에 반응하거나 이 컬렉션을 변경하는 F# Azure Functions 생성을 통해.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-148">Through the creation of F# Azure Functions which react to or cause changes to Azure Cosmos DB collections.</span></span> <span data-ttu-id="6ecfb-149">[Azure Functions의 Azure Cosmos DB 바인딩](/azure/azure-functions/functions-bindings-cosmosdb)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-149">See [Azure Cosmos DB bindings for Azure Functions](/azure/azure-functions/functions-bindings-cosmosdb), or</span></span>
2. <span data-ttu-id="6ecfb-150">[SQL API용 Azure Cosmos DB .NET SDK](/azure/cosmos-db/sql-api-sdk-dotnet)를 사용하여.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-150">By using the [Azure Cosmos DB .NET SDK for SQL API](/azure/cosmos-db/sql-api-sdk-dotnet).</span></span> <span data-ttu-id="6ecfb-151">관련 샘플은 C#으로 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-151">The related samples are in C#.</span></span>

## <a name="using-azure-event-hubs-with-f"></a><span data-ttu-id="6ecfb-152">F\#과 함께 Azure Event Hubs 사용</span><span class="sxs-lookup"><span data-stu-id="6ecfb-152">Using Azure Event Hubs with F\#</span></span>

<span data-ttu-id="6ecfb-153">[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/)는 웹 사이트, 앱 및 디바이스에서 클라우드 규모의 원격 분석 수집을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-153">[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/) provide cloud-scale telemetry ingestion from websites, apps, and devices.</span></span>

<span data-ttu-id="6ecfb-154">Azure Event Hubs는 다음과 같은 두 가지 방법으로 F#과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-154">Azure Event Hubs can be used with F# in two ways:</span></span>

1. <span data-ttu-id="6ecfb-155">이벤트에 의해 트리거되는 F# Azure Functions의 생성을 통해.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-155">Through the creation of F# Azure Functions which are triggered by events.</span></span> <span data-ttu-id="6ecfb-156">[Event Hubs에 대한 Azure Function 트리거](/azure/azure-functions/functions-bindings-event-hubs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-156">See [Azure Function triggers for Event Hubs](/azure/azure-functions/functions-bindings-event-hubs), or</span></span>
2. <span data-ttu-id="6ecfb-157">[Azure용 .NET SDK](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted)를 사용하여.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-157">By using the [.NET SDK for Azure](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted).</span></span> <span data-ttu-id="6ecfb-158">이러한 예제는 C#으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-158">Note these examples are in C#.</span></span>

## <a name="using-azure-notification-hubs-with-f"></a><span data-ttu-id="6ecfb-159">F\#과 함께 Azure Notification Hubs 사용</span><span class="sxs-lookup"><span data-stu-id="6ecfb-159">Using Azure Notification Hubs with F\#</span></span>

<span data-ttu-id="6ecfb-160">[Azure Notification Hubs](/azure/notification-hubs/)는 백 엔드(클라우드 또는 온-프레미스)에서 임의의 모바일 플랫폼으로 모바일 푸시 알림을 보낼 수 있도록 지원하는 다중 플랫폼의 확장된 푸시 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-160">[Azure Notification Hubs](/azure/notification-hubs/) are multiplatform, scaled-out push infrastructure that enable you to send mobile push notifications from any backend (in the cloud or on-premises) to any mobile platform.</span></span>

<span data-ttu-id="6ecfb-161">Azure Notification Hubs는 다음과 같은 두 가지 방법으로 F#과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-161">Azure Notification Hubs can be used with F# in two ways:</span></span>

1. <span data-ttu-id="6ecfb-162">알림 허브로 결과를 보내는 F# Azure Functions 생성을 통해.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-162">Through the creation of F# Azure Functions which send results to a notification hub.</span></span> <span data-ttu-id="6ecfb-163">[Notification Hubs에 대한 Azure Function 출력 트리거](/azure/azure-functions/functions-bindings-notification-hubs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-163">See [Azure Function output triggers for Notification Hubs](/azure/azure-functions/functions-bindings-notification-hubs), or</span></span>
2. <span data-ttu-id="6ecfb-164">[Azure용 .NET SDK](/archive/blogs/azuremobile/push-notifications-using-notification-hub-and-net-backend)를 사용하여.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-164">By using the [.NET SDK for Azure](/archive/blogs/azuremobile/push-notifications-using-notification-hub-and-net-backend).</span></span> <span data-ttu-id="6ecfb-165">이러한 예제는 C#으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-165">Note these examples are in C#.</span></span>

## <a name="implementing-webhooks-on-azure-with-f"></a><span data-ttu-id="6ecfb-166">F\#을 사용하여 Azure에서 WebHook 구현</span><span class="sxs-lookup"><span data-stu-id="6ecfb-166">Implementing WebHooks on Azure with F\#</span></span>

<span data-ttu-id="6ecfb-167">[Webhook](https://en.wikipedia.org/wiki/Webhook)는 웹 요청을 통해 트리거되는 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-167">A [Webhook](https://en.wikipedia.org/wiki/Webhook) is a callback triggered via a web request.</span></span> <span data-ttu-id="6ecfb-168">Webhook는 신호 이벤트에 대한 GitHub와 같은 사이트에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-168">Webhooks are used by sites such as GitHub to signal events.</span></span>

<span data-ttu-id="6ecfb-169">Webhook는 [F#의 Azure Function 및 Webhook 바인딩](/azure/azure-functions/functions-bindings-http-webhook)을 통해 Azure에서 F#으로 구현하고 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-169">Webhooks can be implemented in F# and hosted on Azure via an [Azure Function in F# with a Webhook Binding](/azure/azure-functions/functions-bindings-http-webhook).</span></span>

## <a name="using-webjobs-with-f"></a><span data-ttu-id="6ecfb-170">F\#과 함께 WebJobs 사용</span><span class="sxs-lookup"><span data-stu-id="6ecfb-170">Using Webjobs with F\#</span></span>

<span data-ttu-id="6ecfb-171">[WebJobs](/azure/app-service-web/web-sites-create-web-jobs)는 주문형, 지속형, 예약형의 세 가지 방법으로 App Service 웹앱에서 실행할 수 있는 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-171">[Webjobs](/azure/app-service-web/web-sites-create-web-jobs) are programs you can run in your App Service web app in three ways: on demand, continuously, or on a schedule.</span></span>

[<span data-ttu-id="6ecfb-172">예제 F# WebJobs</span><span class="sxs-lookup"><span data-stu-id="6ecfb-172">Example F# Webjob</span></span>](https://github.com/jrr/webjob-project-examples)

## <a name="implementing-timers-on-azure-with-f"></a><span data-ttu-id="6ecfb-173">F\#을 사용하여 Azure에서 타이머 구현</span><span class="sxs-lookup"><span data-stu-id="6ecfb-173">Implementing Timers on Azure with F\#</span></span>

<span data-ttu-id="6ecfb-174">타이머는 일정, 한 번 또는 되풀이에 따라 호출 함수를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-174">Timer triggers call functions based on a schedule, one time or recurring.</span></span>

<span data-ttu-id="6ecfb-175">타이머는 [F#의 Azure Function 및 타이머 트리거](/azure/azure-functions/functions-bindings-timer)를 통해 Azure에서 F#으로 구현하고 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-175">Timers can be implemented in F# and hosted on Azure via an [Azure Function in F# with a Timer Trigger](/azure/azure-functions/functions-bindings-timer).</span></span>

## <a name="deploying-and-managing-azure-resources-with-f-scripts"></a><span data-ttu-id="6ecfb-176">F# 스크립트를 통해 Azure 리소스 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="6ecfb-176">Deploying and Managing Azure Resources with F# Scripts</span></span>

<span data-ttu-id="6ecfb-177">Azure VM은 Microsoft.Azure.Management 패키지 및 API를 사용하여 프로그래밍 방식으로 배포하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-177">Azure VMs may be programmatically deployed and managed from F# scripts by using the Microsoft.Azure.Management packages and APIs.</span></span> <span data-ttu-id="6ecfb-178">예를 들어 [.NET용 관리 라이브러리 시작](/previous-versions/azure/dn722415(v=azure.100)) 및 [Azure Resource Manager 사용](/azure/azure-resource-manager/resource-manager-deployment-model)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-178">For example, see [Get Started with the Management Libraries for .NET](/previous-versions/azure/dn722415(v=azure.100)) and [Using Azure Resource Manager](/azure/azure-resource-manager/resource-manager-deployment-model).</span></span>

<span data-ttu-id="6ecfb-179">마찬가지로, 동일한 구성 요소를 사용하여 F# 스크립트에서 다른 Azure 리소스를 배포하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-179">Likewise, other Azure resources may also be deployed and managed from F# scripts using the same components.</span></span> <span data-ttu-id="6ecfb-180">예를 들어 F# 스크립트에서 프로그래밍 방식으로 스토리지 계정을 만들고, Azure Cloud Services를 배포하고, Azure Cosmos DB 인스턴스를 만들고, Azure Notifcation Hubs를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-180">For example, you can create storage accounts, deploy Azure Cloud Services, create Azure Cosmos DB instances and manage Azure Notification Hubs programmatically from F# scripts.</span></span>

<span data-ttu-id="6ecfb-181">F# 스크립트를 사용하여 리소스를 배포하고 관리하는 작업은 일반적으로 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-181">Using F# scripts to deploy and manage resources is not normally necessary.</span></span> <span data-ttu-id="6ecfb-182">예를 들어 Azure 리소스는 JSON 템플릿 설명에서 직접 배포할 수도 있습니다(매개 변수화할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="6ecfb-182">For example, Azure resources may also be deployed directly from JSON template descriptions, which can be parameterized.</span></span> <span data-ttu-id="6ecfb-183">[Azure 퀵 스타트 템플릿](https://azure.microsoft.com/resources/templates/)과 같은 예제를 비롯하여 [Azure Resource Manager 템플릿](/azure/azure-resource-manager/resource-manager-template-best-practices)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-183">See [Azure Resource Manager Templates](/azure/azure-resource-manager/resource-manager-template-best-practices) including examples such as the [Azure Quickstart Templates](https://azure.microsoft.com/resources/templates/).</span></span>

## <a name="other-resources"></a><span data-ttu-id="6ecfb-184">기타 리소스</span><span class="sxs-lookup"><span data-stu-id="6ecfb-184">Other resources</span></span>

* [<span data-ttu-id="6ecfb-185">모든 Azure 서비스에 대한 전체 설명서</span><span class="sxs-lookup"><span data-stu-id="6ecfb-185">Full documentation on all Azure services</span></span>](/azure/)
