---
title: 서버리스 앱 샘플 비즈니스 시나리오 및 사용 사례
description: 이미지 처리에서 모바일 지원 및 ETL 파이프라인까지 다양한 샘플에 액세스하여 실습 방식으로 서버리스에 대해 알아봅니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/17/2020
ms.openlocfilehash: 3cb3b73325fccc327ccf17f7298048f2eeb3577a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158452"
---
# <a name="serverless-business-scenarios-and-use-cases"></a><span data-ttu-id="ffc6e-103">서버리스 비즈니스 시나리오 및 사용 사례</span><span class="sxs-lookup"><span data-stu-id="ffc6e-103">Serverless business scenarios and use cases</span></span>

<span data-ttu-id="ffc6e-104">서버리스 애플리케이션에는 다양한 사용 사례 및 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-104">There are many use cases and scenarios for serverless applications.</span></span> <span data-ttu-id="ffc6e-105">이 장에서는 다양한 시나리오를 예시하는 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-105">This chapter includes samples that illustrate the different scenarios.</span></span> <span data-ttu-id="ffc6e-106">시나리오에는 관련 설명서 및 공개 소스 코드 리포지토리에 대한 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-106">The scenarios include links to related documentation and public source code repositories.</span></span> <span data-ttu-id="ffc6e-107">이 장의 샘플을 사용하여 서버리스 솔루션을 직접 빌드하고 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-107">The samples in this chapter enable you to get started on your own building and implementing serverless solutions.</span></span>

## <a name="big-data-processing"></a><span data-ttu-id="ffc6e-108">빅 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="ffc6e-108">Big data processing</span></span>

![Map/reduce 다이어그램](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/media/mapreducearchitecture.png)

<span data-ttu-id="ffc6e-110">이 예제에서는 서버리스를 사용하여 빅 데이터 세트에서 map/reduce 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-110">This example uses serverless to do a map/reduce operation on a big data set.</span></span> <span data-ttu-id="ffc6e-111">2017년에서 일별 뉴욕 노란색 택시 트립의 평균 속도를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-111">It determines the average speed of New York Yellow taxi trips per day in 2017.</span></span>

[<span data-ttu-id="ffc6e-112">빅 데이터 처리: Azure에서 서버리스 MapReduce</span><span class="sxs-lookup"><span data-stu-id="ffc6e-112">Big Data Processing: Serverless MapReduce on Azure</span></span>](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)

## <a name="create-serverless-applications-hands-on-lab"></a><span data-ttu-id="ffc6e-113">서버리스 애플리케이션 만들기: 실습 랩</span><span class="sxs-lookup"><span data-stu-id="ffc6e-113">Create serverless applications: hands-on lab</span></span>

<span data-ttu-id="ffc6e-114">함수를 사용하여 서버 쪽 논리를 실행하고 서버리스 아키텍처를 빌드하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-114">Learn how to use functions to execute server-side logic and build serverless architectures.</span></span>

- <span data-ttu-id="ffc6e-115">비즈니스에 가장 적합한 Azure 서비스 선택</span><span class="sxs-lookup"><span data-stu-id="ffc6e-115">Choosing the best Azure service for your business</span></span>
- <span data-ttu-id="ffc6e-116">Azure Functions 만들기</span><span class="sxs-lookup"><span data-stu-id="ffc6e-116">Creating Azure Functions</span></span>
- <span data-ttu-id="ffc6e-117">트리거 사용</span><span class="sxs-lookup"><span data-stu-id="ffc6e-117">Using triggers</span></span>
- <span data-ttu-id="ffc6e-118">체이닝 함수</span><span class="sxs-lookup"><span data-stu-id="ffc6e-118">Chaining functions</span></span>
- <span data-ttu-id="ffc6e-119">장기 실행 워크플로</span><span class="sxs-lookup"><span data-stu-id="ffc6e-119">Long-running workflows</span></span>
- <span data-ttu-id="ffc6e-120">모니터링</span><span class="sxs-lookup"><span data-stu-id="ffc6e-120">Monitoring</span></span>
- <span data-ttu-id="ffc6e-121">개발, 테스트 및 배포</span><span class="sxs-lookup"><span data-stu-id="ffc6e-121">Development, testing, and deployment</span></span>

[<span data-ttu-id="ffc6e-122">서버리스 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="ffc6e-122">Create serverless applications</span></span>](https://docs.microsoft.com/learn/paths/create-serverless-applications/)

## <a name="customer-reviews"></a><span data-ttu-id="ffc6e-123">고객 리뷰</span><span class="sxs-lookup"><span data-stu-id="ffc6e-123">Customer reviews</span></span>

<span data-ttu-id="ffc6e-124">이 샘플에서는 Visual Studio의 C# 클래스 라이브러리에 대한 새로운 Azure Functions 도구를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-124">This sample showcases the new Azure Functions tooling for C# Class Libraries in Visual Studio.</span></span> <span data-ttu-id="ffc6e-125">고객이 Azure 스토리지 Blob 및 CosmosDB에 저장된 제품 검토를 제출하는 웹 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-125">Create a website where customers submit product reviews that are stored in Azure storage blobs and CosmosDB.</span></span> <span data-ttu-id="ffc6e-126">Azure Cognitive Services를 사용하여 고객 리뷰의 자동화된 중재를 수행하는 Azure 함수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-126">Add an Azure Function to perform automated moderation of the customer reviews using Azure Cognitive Services.</span></span> <span data-ttu-id="ffc6e-127">Azure 스토리지 큐를 사용하여 기능에서 웹 사이트를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-127">Use an Azure storage queue to decouple the website from the function.</span></span>

[<span data-ttu-id="ffc6e-128">Cognitive Services로 고객 리뷰 앱</span><span class="sxs-lookup"><span data-stu-id="ffc6e-128">Customer Reviews App with Cognitive Services</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)

## <a name="docker-linux-image-support"></a><span data-ttu-id="ffc6e-129">Docker Linux 이미지 지원</span><span class="sxs-lookup"><span data-stu-id="ffc6e-129">Docker Linux image support</span></span>

<span data-ttu-id="ffc6e-130">이 샘플은 Linux Docker 컨테이너에서 Azure Functions를 빌드하고 실행하는 `Dockerfile`을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-130">This sample demonstrates how to create a `Dockerfile` to build and run Azure Functions on a Linux Docker container.</span></span>

[<span data-ttu-id="ffc6e-131">Linux에서 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="ffc6e-131">Azure Functions on Linux</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)

## <a name="file-processing-and-validation"></a><span data-ttu-id="ffc6e-132">파일 처리 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ffc6e-132">File processing and validation</span></span>

<span data-ttu-id="ffc6e-133">이 예제에서는 가상 고객의 CSV 파일 세트를 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-133">This example parses a set of CSV files from hypothetical customers.</span></span> <span data-ttu-id="ffc6e-134">고객 "일괄 처리"에 필요한 모든 파일이 준비되었는지 확인한 다음, 각 파일 구조의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-134">It ensures that all files required for a customer "batch" are ready, then validates the structure of each file.</span></span> <span data-ttu-id="ffc6e-135">Azure Functions, Logic Apps 및 Durable Functions를 사용하여 다양한 솔루션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-135">Different solutions are presented using Azure Functions, Logic Apps, and Durable Functions.</span></span>

[<span data-ttu-id="ffc6e-136">Azure Functions, Logic Apps 및 Durable Functions를 사용하여 파일 처리 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ffc6e-136">File processing and validation using Azure Functions, Logic Apps, and Durable Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)

## <a name="game-data-visualization"></a><span data-ttu-id="ffc6e-137">게임 데이터 시각화</span><span class="sxs-lookup"><span data-stu-id="ffc6e-137">Game data visualization</span></span>

![게임 원격 분석](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/media/points.png)

<span data-ttu-id="ffc6e-139">개발자가 게임에 대한 편집기 내 데이터 시각화 솔루션을 구현하는 방법의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-139">An example of how a developer could implement an in-editor data visualization solution for their game.</span></span> <span data-ttu-id="ffc6e-140">실제로 이 샘플을 백 엔드로 사용하여 Unreal Engine 4 플러그 인 및 Unity 플러그 인을 개발했습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-140">In fact, an Unreal Engine 4 Plugin and Unity Plugin were developed using this sample as its backend.</span></span> <span data-ttu-id="ffc6e-141">서비스 구성 요소는 게임 엔진에 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-141">The service component is game engine agnostic.</span></span>

[<span data-ttu-id="ffc6e-142">편집기 내 게임 원격 분석 시각화</span><span class="sxs-lookup"><span data-stu-id="ffc6e-142">In-editor game telemetry visualization</span></span>](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)

## <a name="graphql"></a><span data-ttu-id="ffc6e-143">GraphQL</span><span class="sxs-lookup"><span data-stu-id="ffc6e-143">GraphQL</span></span>

<span data-ttu-id="ffc6e-144">GraphQL API를 노출하는 서버리스 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-144">Create a serverless function that exposes a GraphQL API.</span></span>

[<span data-ttu-id="ffc6e-145">GraphQL에 대한 서버리스 함수</span><span class="sxs-lookup"><span data-stu-id="ffc6e-145">Serverless functions for GraphQL</span></span>](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)

## <a name="internet-of-things-iot-reliable-edge-relay"></a><span data-ttu-id="ffc6e-146">IoT(사물 인터넷) 안정적인 에지 릴레이</span><span class="sxs-lookup"><span data-stu-id="ffc6e-146">Internet of Things (IoT) reliable edge relay</span></span>

![IoT 아키텍처](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/media/architecture.png)

<span data-ttu-id="ffc6e-148">이 샘플은 IoT 디바이스에서 안정적인 업스트림 통신을 가능하게 하는 새로운 통신 프로토콜을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-148">This sample implements a new communication protocol to enable reliable upstream communication from IoT devices.</span></span> <span data-ttu-id="ffc6e-149">데이터 갭 검색 및 백필을 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-149">It automates data gap detection and backfill.</span></span>

[<span data-ttu-id="ffc6e-150">IoT 안정적인 에지 릴레이</span><span class="sxs-lookup"><span data-stu-id="ffc6e-150">IoT Reliable Edge Relay</span></span>](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)

## <a name="microservices-reference-architecture"></a><span data-ttu-id="ffc6e-151">마이크로서비스 참조 아키텍처</span><span class="sxs-lookup"><span data-stu-id="ffc6e-151">Microservices reference architecture</span></span>

![참조 아키텍처](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/media/macro-architecture.png)

<span data-ttu-id="ffc6e-153">가상 회사인 Relecloud 애플리케이션을 통해 Rideshare를 디자인, 개발 및 제공하는 것과 관련된 의사 결정 과정을 안내하는 참조 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-153">A reference architecture that walks you through the decision-making process involved in designing, developing, and delivering the Rideshare by Relecloud application (a fictitious company).</span></span> <span data-ttu-id="ffc6e-154">여기에는 모든 아키텍처의 구성 요소를 구성하고 배포하기 위한 실습 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-154">It includes hands-on instructions for configuring and deploying all of the architecture's components.</span></span>

[<span data-ttu-id="ffc6e-155">서버리스 마이크로서비스 참조 아키텍처</span><span class="sxs-lookup"><span data-stu-id="ffc6e-155">Serverless Microservices reference architecture</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

## <a name="migrate-console-apps-to-serverless"></a><span data-ttu-id="ffc6e-156">서버리스로 콘솔 앱 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ffc6e-156">Migrate console apps to serverless</span></span>

<span data-ttu-id="ffc6e-157">이 샘플은 Azure Functions의 모든 콘솔 애플리케이션을 HTTP 웹 서비스로 변환하는 데 사용할 수 있는 제네릭 함수(`.csx` 파일)입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-157">This sample is a generic function (`.csx` file) that can be used to convert any console application to an HTTP web service in Azure Functions.</span></span> <span data-ttu-id="ffc6e-158">구성 파일을 편집하고 인수로 `.exe`에 전달되는 입력 매개 변수를 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-158">All you have to do is edit a configuration file and specify what input parameters will be passed as arguments to the `.exe`.</span></span>

[<span data-ttu-id="ffc6e-159">Azure Functions에서 콘솔 앱 실행</span><span class="sxs-lookup"><span data-stu-id="ffc6e-159">Run Console Apps on Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)

## <a name="serverless-for-mobile"></a><span data-ttu-id="ffc6e-160">모바일에 대한 서버리스</span><span class="sxs-lookup"><span data-stu-id="ffc6e-160">Serverless for mobile</span></span>

<span data-ttu-id="ffc6e-161">Azure Functions는 쉽게 구현하고 유지 관리할 수 있으며 HTTP를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-161">Azure Functions are easy to implement and maintain, and accessible through HTTP.</span></span> <span data-ttu-id="ffc6e-162">모바일 애플리케이션에 대한 API를 구현하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-162">They are a great way to implement an API for a mobile application.</span></span> <span data-ttu-id="ffc6e-163">Microsoft는 Xamarin을 사용하여 iOS, Android 및 Windows용 플랫폼 간 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-163">Microsoft offers great cross-platform tools for iOS, Android, and Windows with Xamarin.</span></span> <span data-ttu-id="ffc6e-164">따라서 Xamarin 및 Azure Functions는 함께 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-164">As such, Xamarin and Azure Functions are working great together.</span></span> <span data-ttu-id="ffc6e-165">이 문서에서는 먼저 Azure Portal 또는 Visual Studio에서 Azure 함수를 구현하고, Android, iOS 및 Windows에서 실행되는 Xamarin.Forms를 사용하여 플랫폼 간 클라이언트를 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-165">This article shows how to implement an Azure Function in the Azure portal or in Visual Studio at first, and build a cross-platform client with Xamarin.Forms running on Android, iOS, and Windows.</span></span>

[<span data-ttu-id="ffc6e-166">Xamarin.Forms 클라이언트를 사용하여 간단한 Azure Function 구현</span><span class="sxs-lookup"><span data-stu-id="ffc6e-166">Implementing a simple Azure Function with a Xamarin.Forms client</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)

## <a name="serverless-messaging"></a><span data-ttu-id="ffc6e-167">서버리스 메시징</span><span class="sxs-lookup"><span data-stu-id="ffc6e-167">Serverless messaging</span></span>

<span data-ttu-id="ffc6e-168">이 샘플에서는 Durable Functions의 팬 아웃 패턴을 활용하여 원하는 수의 세션/파티션에 걸쳐 임의 개수의 메시지를 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-168">This sample shows how to utilize Durable Functions' fan-out pattern to load an arbitrary number of messages across any number of sessions/partitions.</span></span> <span data-ttu-id="ffc6e-169">Service Bus, Event Hubs 또는 Storage 큐를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-169">It targets Service Bus, Event Hubs, or Storage Queues.</span></span> <span data-ttu-id="ffc6e-170">또한 이 샘플에서는 다른 Azure 함수를 사용하여 이러한 메시지를 사용하는 기능을 추가하고 결과 타이밍 데이터를 다른 이벤트 허브에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-170">The sample also adds the ability to consume those messages with another Azure Function and load the resulting timing data in to another Event Hub.</span></span> <span data-ttu-id="ffc6e-171">그런 다음, 데이터는 Azure Data Explorer와 같은 분석 서비스로 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-171">The data is then ingested into analytics services like Azure Data Explorer.</span></span>

[<span data-ttu-id="ffc6e-172">Azure Functions를 사용하여 Service Bus, Event Hubs 및 Storage 큐를 통해 메시지 생성 및 사용</span><span class="sxs-lookup"><span data-stu-id="ffc6e-172">Produce and Consume messages through Service Bus, Event Hubs, and Storage Queues with Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)

## <a name="recommended-resources"></a><span data-ttu-id="ffc6e-173">권장되는 리소스</span><span class="sxs-lookup"><span data-stu-id="ffc6e-173">Recommended resources</span></span>

- [<span data-ttu-id="ffc6e-174">Linux에서 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="ffc6e-174">Azure Functions on Linux</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)
- [<span data-ttu-id="ffc6e-175">빅 데이터 처리: Azure에서 서버리스 MapReduce</span><span class="sxs-lookup"><span data-stu-id="ffc6e-175">Big Data Processing: Serverless MapReduce on Azure</span></span>](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)
- [<span data-ttu-id="ffc6e-176">서버리스 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="ffc6e-176">Create serverless applications</span></span>](https://docs.microsoft.com/learn/paths/create-serverless-applications/)
- [<span data-ttu-id="ffc6e-177">Cognitive Services로 고객 리뷰 앱</span><span class="sxs-lookup"><span data-stu-id="ffc6e-177">Customer Reviews App with Cognitive Services</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)
- [<span data-ttu-id="ffc6e-178">Azure Functions, Logic Apps 및 Durable Functions를 사용하여 파일 처리 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ffc6e-178">File processing and validation using Azure Functions, Logic Apps, and Durable Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)
- [<span data-ttu-id="ffc6e-179">Xamarin.Forms 클라이언트를 사용하여 간단한 Azure Function 구현</span><span class="sxs-lookup"><span data-stu-id="ffc6e-179">Implementing a simple Azure Function with a Xamarin.Forms client</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [<span data-ttu-id="ffc6e-180">편집기 내 게임 원격 분석 시각화</span><span class="sxs-lookup"><span data-stu-id="ffc6e-180">In-editor game telemetry visualization</span></span>](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)
- [<span data-ttu-id="ffc6e-181">IoT 안정적인 에지 릴레이</span><span class="sxs-lookup"><span data-stu-id="ffc6e-181">IoT Reliable Edge Relay</span></span>](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)
- [<span data-ttu-id="ffc6e-182">Azure Functions를 사용하여 Service Bus, Event Hubs 및 Storage 큐를 통해 메시지 생성 및 사용</span><span class="sxs-lookup"><span data-stu-id="ffc6e-182">Produce and Consume messages through Service Bus, Event Hubs, and Storage Queues with Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)
- [<span data-ttu-id="ffc6e-183">Azure Functions에서 콘솔 앱 실행</span><span class="sxs-lookup"><span data-stu-id="ffc6e-183">Run Console Apps on Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)
- [<span data-ttu-id="ffc6e-184">GraphQL에 대한 서버리스 함수</span><span class="sxs-lookup"><span data-stu-id="ffc6e-184">Serverless functions for GraphQL</span></span>](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)
- [<span data-ttu-id="ffc6e-185">서버리스 마이크로서비스 참조 아키텍처</span><span class="sxs-lookup"><span data-stu-id="ffc6e-185">Serverless Microservices reference architecture</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

>[!div class="step-by-step"]
><span data-ttu-id="ffc6e-186">[이전](orchestration-patterns.md)
>[다음](serverless-conclusion.md)</span><span class="sxs-lookup"><span data-stu-id="ffc6e-186">[Previous](orchestration-patterns.md)
[Next](serverless-conclusion.md)</span></span>
