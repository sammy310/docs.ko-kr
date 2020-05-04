---
title: Azure Functions - 서버리스 앱
description: Azure Functions는 여러 언어(C#, JavaScript, Java) 및 플랫폼에서 서버리스 기능을 제공하여 이벤트 기반 즉시 크기 조정 코드를 제공합니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 2dee60e3635be94a55ee26a7f04942bc59cb8dec
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135726"
---
# <a name="azure-functions"></a><span data-ttu-id="d9fd1-103">Azure Functions</span><span class="sxs-lookup"><span data-stu-id="d9fd1-103">Azure Functions</span></span>

<span data-ttu-id="d9fd1-104">Azure 함수는 서버리스 컴퓨팅 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="d9fd1-105">함수는 *트리거*(예: HTTP 엔드포인트 또는 타이머에 대한 액세스)에 의해 호출되며, 코드 블록 또는 비즈니스 논리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="d9fd1-106">또한 함수는 저장소 및 큐와 같은 리소스에 연결하는 특수 *바인딩*을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure Functions 로고](./media/azure-functions-logo.png)

<span data-ttu-id="d9fd1-108">현재 런타임 버전 3.0은 플랫폼 간 .NET Core 3.1 애플리케이션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-108">The current runtime version 3.0 supports cross-platform .NET Core 3.1 applications.</span></span> <span data-ttu-id="d9fd1-109">C# 이외에 JavaScript, F#, Java 같은 언어를 추가로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-109">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="d9fd1-110">포털에서 만든 함수는 풍부한 스크립팅 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-110">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="d9fd1-111">독립 실행형 프로젝트로 만들어진 함수는 전체 플랫폼 지원 및 기능을 사용하여 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-111">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="d9fd1-112">자세한 내용은 [Azure Functions 팩](https://docs.microsoft.com/azure/azure-functions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-112">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="d9fd1-113">프로그래밍 언어 지원</span><span class="sxs-lookup"><span data-stu-id="d9fd1-113">Programming language support</span></span>

<span data-ttu-id="d9fd1-114">다음 언어는 모두 GA(일반 공급)로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-114">The following languages are all supported in general availability (GA).</span></span>

|<span data-ttu-id="d9fd1-115">언어</span><span class="sxs-lookup"><span data-stu-id="d9fd1-115">Language</span></span>      |<span data-ttu-id="d9fd1-116">지원되는 런타임</span><span class="sxs-lookup"><span data-stu-id="d9fd1-116">Supported runtimes</span></span>|
|--------------|------------------|
|<span data-ttu-id="d9fd1-117">**C#**</span><span class="sxs-lookup"><span data-stu-id="d9fd1-117">**C#**</span></span>        |<span data-ttu-id="d9fd1-118">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d9fd1-118">.NET Core 3.1</span></span>     |
|<span data-ttu-id="d9fd1-119">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="d9fd1-119">**JavaScript**</span></span>|<span data-ttu-id="d9fd1-120">Node 10 및 12</span><span class="sxs-lookup"><span data-stu-id="d9fd1-120">Node 10 & 12</span></span>      |
|<span data-ttu-id="d9fd1-121">**F#**</span><span class="sxs-lookup"><span data-stu-id="d9fd1-121">**F#**</span></span>        |<span data-ttu-id="d9fd1-122">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d9fd1-122">.NET Core 3.1</span></span>     |
|<span data-ttu-id="d9fd1-123">**Java**</span><span class="sxs-lookup"><span data-stu-id="d9fd1-123">**Java**</span></span>      |<span data-ttu-id="d9fd1-124">Java 8</span><span class="sxs-lookup"><span data-stu-id="d9fd1-124">Java 8</span></span>            |
|<span data-ttu-id="d9fd1-125">**Python**</span><span class="sxs-lookup"><span data-stu-id="d9fd1-125">**Python**</span></span>    |<span data-ttu-id="d9fd1-126">Python 3.6, 3.7 및 3.8</span><span class="sxs-lookup"><span data-stu-id="d9fd1-126">Python 3.6, 3.7, & 3.8</span></span>|
|<span data-ttu-id="d9fd1-127">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="d9fd1-127">**TypeScript**</span></span>|<span data-ttu-id="d9fd1-128">Node 10 및 12(JavaScript를 통해)</span><span class="sxs-lookup"><span data-stu-id="d9fd1-128">Node 10 & 12 (via JavaScript)</span></span>|
|<span data-ttu-id="d9fd1-129">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d9fd1-129">**PowerShell**</span></span>|<span data-ttu-id="d9fd1-130">PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="d9fd1-130">PowerShell Core 6</span></span>|

<span data-ttu-id="d9fd1-131">자세한 내용은 [지원되는 언어](https://docs.microsoft.com/azure/azure-functions/supported-languages)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-131">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="d9fd1-132">App Service 계획</span><span class="sxs-lookup"><span data-stu-id="d9fd1-132">App service plans</span></span>

<span data-ttu-id="d9fd1-133">함수는 *App Service 계획*으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-133">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="d9fd1-134">계획은 함수 앱에서 사용하는 리소스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-134">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="d9fd1-135">지역에 계획을 할당하고, 사용되는 가상 머신의 크기 및 수를 결정하고, 가격 책정 계층을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-135">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="d9fd1-136">진정한 서버리스 접근 방식을 위해 함수 앱에서 **사용** 계획을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-136">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="d9fd1-137">사용 계획은 부하에 따라 자동으로 백 엔드 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-137">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="d9fd1-138">함수 앱에 대한 또 하나의 호스팅 옵션은 [프리미엄 플랜](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan)입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-138">Another hosting option for function apps is the [Premium plan](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan).</span></span> <span data-ttu-id="d9fd1-139">이 플랜은 콜드 부팅을 방지하고 VNet 연결과 같은 고급 기능을 지원하며 프리미엄 하드웨어에서 실행되는 "always on" 인스턴스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-139">This plan provides an "always on" instance to avoid cold start, supports advanced features like VNet connectivity, and runs on premium hardware.</span></span>

<span data-ttu-id="d9fd1-140">자세한 내용은 [App Service 계획](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-140">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="d9fd1-141">첫 번째 기능 만들기</span><span class="sxs-lookup"><span data-stu-id="d9fd1-141">Create your first function</span></span>

<span data-ttu-id="d9fd1-142">세 가지 일반적인 방법으로 함수 앱을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-142">There are three common ways you can create function apps.</span></span>

- <span data-ttu-id="d9fd1-143">포털에서 함수를 스크립팅합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-143">Script functions in the portal.</span></span>
- <span data-ttu-id="d9fd1-144">Azure CLI를 사용하여 필요한 리소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-144">Create the necessary resources using the Azure CLI.</span></span>
- <span data-ttu-id="d9fd1-145">즐겨 사용하는 IDE를 사용하여 함수를 로컬에서 빌드하고 Azure에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-145">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="d9fd1-146">포털에서 스크립팅된 함수를 만드는 방법에 대한 자세한 내용은 [Azure Portal에서 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-146">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="d9fd1-147">Azure CLI에서 빌드하려면 [Azure CLI를 사용하여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-147">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="d9fd1-148">Visual Studio에서 함수를 만들려면 [Visual Studio를 사용하여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-148">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="d9fd1-149">트리거 및 바인딩 이해</span><span class="sxs-lookup"><span data-stu-id="d9fd1-149">Understand triggers and bindings</span></span>

<span data-ttu-id="d9fd1-150">함수는 *트리거*에 의해 호출되며 정확히 하나의 함수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-150">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="d9fd1-151">함수를 호출하는 이외에 일부 트리거는 바인딩으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-151">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="d9fd1-152">트리거와 함께 여러 바인딩을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-152">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="d9fd1-153">*바인딩*은 데이터를 코드에 연결하는 선언적 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-153">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="d9fd1-154">이들은 전달되거나(입력) 데이터를 수신할 수 있습니다(출력).</span><span class="sxs-lookup"><span data-stu-id="d9fd1-154">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="d9fd1-155">트리거 및 바인딩을 사용하면 함수를 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-155">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="d9fd1-156">바인딩은 수동으로 데이터베이스 또는 파일 시스템 연결을 만드는 오버헤드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-156">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="d9fd1-157">바인딩에 필요한 모든 정보는 스크립트의 경우 *functions.json* 파일에 포함되거나 코드에서 특성으로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-157">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="d9fd1-158">몇 가지 일반적인 트리거는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-158">Some common triggers include:</span></span>

- <span data-ttu-id="d9fd1-159">Blob Storage: 파일 또는 폴더가 업로드되거나 저장소에서 변경될 때 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-159">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
- <span data-ttu-id="d9fd1-160">HTTP: REST API처럼 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-160">HTTP: invoke your function like a REST API.</span></span>
- <span data-ttu-id="d9fd1-161">큐: 큐에 항목이 있을 때 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-161">Queue: invoke your function when items exist in a queue.</span></span>
- <span data-ttu-id="d9fd1-162">타이머: 정기적으로 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-162">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="d9fd1-163">바인딩의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-163">Examples of bindings include:</span></span>

- <span data-ttu-id="d9fd1-164">CosmosDB: 간편하게 데이터베이스에 연결하여 파일을 로드하거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-164">CosmosDB: easily connect to the database to load or save files.</span></span>
- <span data-ttu-id="d9fd1-165">Table Storage: 함수 앱에서 키/값 저장소로 작업합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-165">Table Storage: work with key/value storage from your function app.</span></span>
- <span data-ttu-id="d9fd1-166">Queue Storage: 간편하게 큐에서 항목을 검색하거나 새 항목을 큐에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-166">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="d9fd1-167">다음 에제 *functions.json* 파일에서는 트리거 및 바인딩을 하나씩 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-167">The following example *functions.json* file defines a trigger and a binding:</span></span>

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

<span data-ttu-id="d9fd1-168">이 예제에서 함수는 `images` 컨테이너의 Blob 스토리지에 대한 변경에 의해 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-168">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="d9fd1-169">파일 정보가 전달되기 때문에 트리거가 바인딩의 역할도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-169">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="d9fd1-170">`images`라는 큐에 정보를 넣는 다른 바인딩이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-170">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="d9fd1-171">다음은 함수에 대한 C# 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-171">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="d9fd1-172">예제는 수정되었거나 Blob 스토리지에 업로드된 파일의 이름을 사용하고 나중에 처리할 수 있도록 큐에 배치하는 간단한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-172">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="d9fd1-173">트리거 및 바인딩의 전체 목록은 [Azure Functions 트리거 및 바인딩 개념](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9fd1-173">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d9fd1-174">[이전](azure-serverless-platform.md)
>[다음](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="d9fd1-174">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
