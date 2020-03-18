---
title: Azure Functions - 서버리스 앱
description: Azure Functions는 여러 언어(C#, JavaScript, Java) 및 플랫폼에서 서버리스 기능을 제공하여 이벤트 기반 즉시 크기 조정 코드를 제공합니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 8764e6a33f3fdd53e60fa767d0fb584a9c07de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401486"
---
# <a name="azure-functions"></a><span data-ttu-id="1f1ea-103">Azure Functions</span><span class="sxs-lookup"><span data-stu-id="1f1ea-103">Azure Functions</span></span>

<span data-ttu-id="1f1ea-104">Azure 함수는 서버리스 컴퓨팅 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="1f1ea-105">함수는 *트리거*(예: HTTP 엔드포인트 또는 타이머에 대한 액세스)에 의해 호출되며, 코드 블록 또는 비즈니스 논리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="1f1ea-106">또한 함수는 저장소 및 큐와 같은 리소스에 연결하는 특수 *바인딩*을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure Functions 로고](./media/azure-functions-logo.png)

<span data-ttu-id="1f1ea-108">Azure Functions 프레임워크에는 두 가지 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="1f1ea-109">레거시 버전은 전체 .NET Framework를 지원하고 새 런타임은 플랫폼 간 .NET Core 애플리케이션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="1f1ea-110">C# 이외에 JavaScript, F#, Java 같은 언어를 추가로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="1f1ea-111">포털에서 만든 함수는 풍부한 스크립팅 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="1f1ea-112">독립 실행형 프로젝트로 만들어진 함수는 전체 플랫폼 지원 및 기능을 사용하여 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="1f1ea-113">자세한 내용은 [Azure Functions 팩](https://docs.microsoft.com/azure/azure-functions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="1f1ea-114">Functions v1 및 v2</span><span class="sxs-lookup"><span data-stu-id="1f1ea-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="1f1ea-115">Azure Functions 런타임에는 두 가지 버전이 있습니다. 1.x 및 2.x.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="1f1ea-116">버전 1.x는 GA(일반 공급)입니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="1f1ea-117">포털 또는 Windows 컴퓨터에서 .NET 개발을 지원하고 .NET Framework를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="1f1ea-118">1.x는 C#, JavaScript 및 F#를 지원하며 Python, PHP, TypeScript, Batch, Bash 및 PowerShell에 대한 실험적 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="1f1ea-119">[버전 2.x도 이제 일반 공급으로 제공됩니다](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span><span class="sxs-lookup"><span data-stu-id="1f1ea-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="1f1ea-120">.NET Core를 활용하고 Windows, macOS 및 Linux 컴퓨터에서 플랫폼 간 개발을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="1f1ea-121">2.x는 Java에 대한 최고 수준의 지원을 추가했지만 실험적 언어는 아직 직접 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="1f1ea-122">버전 2.x는 플랫폼에 대한 타사 확장, 독립적인 바인딩 버전 관리, 보다 간소화된 실행 환경을 가능하게 하는 새로운 바인딩 확장성 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="1f1ea-123">**1.x는 [바인딩 리디렉션 지원](https://github.com/Azure/azure-functions-host/issues/992)에서 알려진 문제가 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1f1ea-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="1f1ea-124">이 문제는 .NET 개발과 관련된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="1f1ea-125">런타임에 포함된 라이브러리와 다른 버전의 라이브러리에 대한 종속성이 있는 프로젝트가 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="1f1ea-126">함수 팀은 이 문제를 해결하기 위해 최선을 다하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="1f1ea-127">팀은 일반 공급으로 전환하기 전에 2.x의 바인딩 리디렉션을 처리할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="1f1ea-128">다음은 팀에서 공식적으로 제안한 수정 및 해결 방법입니다. [Azure Functions의 어셈블리 분해능](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span><span class="sxs-lookup"><span data-stu-id="1f1ea-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="1f1ea-129">자세한 내용은 [1. x 및 2.x 비교](https://docs.microsoft.com/azure/azure-functions/functions-versions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="1f1ea-130">프로그래밍 언어 지원</span><span class="sxs-lookup"><span data-stu-id="1f1ea-130">Programming language support</span></span>

<span data-ttu-id="1f1ea-131">GA(일반 공급), 미리 보기 또는 실험적으로 지원되는 언어는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="1f1ea-132">언어</span><span class="sxs-lookup"><span data-stu-id="1f1ea-132">Language</span></span>      |<span data-ttu-id="1f1ea-133">1.x</span><span class="sxs-lookup"><span data-stu-id="1f1ea-133">1.x</span></span>         |<span data-ttu-id="1f1ea-134">2.x</span><span class="sxs-lookup"><span data-stu-id="1f1ea-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="1f1ea-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="1f1ea-135">**C#**</span></span>        |<span data-ttu-id="1f1ea-136">GA</span><span class="sxs-lookup"><span data-stu-id="1f1ea-136">GA</span></span>          |<span data-ttu-id="1f1ea-137">미리 보기</span><span class="sxs-lookup"><span data-stu-id="1f1ea-137">Preview</span></span>  |
|<span data-ttu-id="1f1ea-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="1f1ea-138">**JavaScript**</span></span>|<span data-ttu-id="1f1ea-139">GA</span><span class="sxs-lookup"><span data-stu-id="1f1ea-139">GA</span></span>          |<span data-ttu-id="1f1ea-140">미리 보기</span><span class="sxs-lookup"><span data-stu-id="1f1ea-140">Preview</span></span>  |
|<span data-ttu-id="1f1ea-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="1f1ea-141">**F#**</span></span>        |<span data-ttu-id="1f1ea-142">GA</span><span class="sxs-lookup"><span data-stu-id="1f1ea-142">GA</span></span>          |         |
|<span data-ttu-id="1f1ea-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="1f1ea-143">**Java**</span></span>      |            |<span data-ttu-id="1f1ea-144">미리 보기</span><span class="sxs-lookup"><span data-stu-id="1f1ea-144">Preview</span></span>  |
|<span data-ttu-id="1f1ea-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="1f1ea-145">**Python**</span></span>    |<span data-ttu-id="1f1ea-146">실험적</span><span class="sxs-lookup"><span data-stu-id="1f1ea-146">Experimental</span></span>|         |
|<span data-ttu-id="1f1ea-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="1f1ea-147">**PHP**</span></span>       |<span data-ttu-id="1f1ea-148">실험적</span><span class="sxs-lookup"><span data-stu-id="1f1ea-148">Experimental</span></span>|         |
|<span data-ttu-id="1f1ea-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="1f1ea-149">**TypeScript**</span></span>|<span data-ttu-id="1f1ea-150">실험적</span><span class="sxs-lookup"><span data-stu-id="1f1ea-150">Experimental</span></span>|         |
|<span data-ttu-id="1f1ea-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="1f1ea-151">**Batch**</span></span>     |<span data-ttu-id="1f1ea-152">실험적</span><span class="sxs-lookup"><span data-stu-id="1f1ea-152">Experimental</span></span>|         |
|<span data-ttu-id="1f1ea-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="1f1ea-153">**Bash**</span></span>      |<span data-ttu-id="1f1ea-154">실험적</span><span class="sxs-lookup"><span data-stu-id="1f1ea-154">Experimental</span></span>|         |
|<span data-ttu-id="1f1ea-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1f1ea-155">**PowerShell**</span></span>|<span data-ttu-id="1f1ea-156">실험적</span><span class="sxs-lookup"><span data-stu-id="1f1ea-156">Experimental</span></span>|         |

<span data-ttu-id="1f1ea-157">자세한 내용은 [지원되는 언어](https://docs.microsoft.com/azure/azure-functions/supported-languages)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="1f1ea-158">App Service 계획</span><span class="sxs-lookup"><span data-stu-id="1f1ea-158">App service plans</span></span>

<span data-ttu-id="1f1ea-159">함수는 *App Service 계획*으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="1f1ea-160">계획은 함수 앱에서 사용하는 리소스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="1f1ea-161">지역에 계획을 할당하고, 사용되는 가상 머신의 크기 및 수를 결정하고, 가격 책정 계층을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="1f1ea-162">진정한 서버리스 접근 방식을 위해 함수 앱에서 **사용** 계획을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="1f1ea-163">사용 계획은 부하에 따라 자동으로 백 엔드 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="1f1ea-164">자세한 내용은 [App Service 계획](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="1f1ea-165">첫 번째 기능 만들기</span><span class="sxs-lookup"><span data-stu-id="1f1ea-165">Create your first function</span></span>

<span data-ttu-id="1f1ea-166">세 가지 일반적인 방법으로 함수 앱을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-166">There are three common ways you can create function apps.</span></span>

- <span data-ttu-id="1f1ea-167">포털에서 함수를 스크립팅합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-167">Script functions in the portal.</span></span>
- <span data-ttu-id="1f1ea-168">Azure CLI를 사용하여 필요한 리소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-168">Create the necessary resources using the Azure CLI.</span></span>
- <span data-ttu-id="1f1ea-169">즐겨 사용하는 IDE를 사용하여 함수를 로컬에서 빌드하고 Azure에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="1f1ea-170">포털에서 스크립팅된 함수를 만드는 방법에 대한 자세한 내용은 [Azure Portal에서 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="1f1ea-171">Azure CLI에서 빌드하려면 [Azure CLI를 사용하여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="1f1ea-172">Visual Studio에서 함수를 만들려면 [Visual Studio를 사용하여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="1f1ea-173">트리거 및 바인딩 이해</span><span class="sxs-lookup"><span data-stu-id="1f1ea-173">Understand triggers and bindings</span></span>

<span data-ttu-id="1f1ea-174">함수는 *트리거*에 의해 호출되며 정확히 하나의 함수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="1f1ea-175">함수를 호출하는 이외에 일부 트리거는 바인딩으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="1f1ea-176">트리거와 함께 여러 바인딩을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="1f1ea-177">*바인딩*은 데이터를 코드에 연결하는 선언적 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="1f1ea-178">이들은 전달되거나(입력) 데이터를 수신할 수 있습니다(출력).</span><span class="sxs-lookup"><span data-stu-id="1f1ea-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="1f1ea-179">트리거 및 바인딩을 사용하면 함수를 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="1f1ea-180">바인딩은 수동으로 데이터베이스 또는 파일 시스템 연결을 만드는 오버헤드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="1f1ea-181">바인딩에 필요한 모든 정보는 스크립트의 경우 *functions.json* 파일에 포함되거나 코드에서 특성으로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="1f1ea-182">몇 가지 일반적인 트리거는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-182">Some common triggers include:</span></span>

- <span data-ttu-id="1f1ea-183">Blob Storage: 파일 또는 폴더가 업로드되거나 저장소에서 변경될 때 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
- <span data-ttu-id="1f1ea-184">HTTP: REST API처럼 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-184">HTTP: invoke your function like a REST API.</span></span>
- <span data-ttu-id="1f1ea-185">큐: 큐에 항목이 있을 때 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-185">Queue: invoke your function when items exist in a queue.</span></span>
- <span data-ttu-id="1f1ea-186">타이머: 정기적으로 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="1f1ea-187">바인딩의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-187">Examples of bindings include:</span></span>

- <span data-ttu-id="1f1ea-188">CosmosDB: 간편하게 데이터베이스에 연결하여 파일을 로드하거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-188">CosmosDB: easily connect to the database to load or save files.</span></span>
- <span data-ttu-id="1f1ea-189">Table Storage: 함수 앱에서 키/값 저장소로 작업합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-189">Table Storage: work with key/value storage from your function app.</span></span>
- <span data-ttu-id="1f1ea-190">Queue Storage: 간편하게 큐에서 항목을 검색하거나 새 항목을 큐에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="1f1ea-191">다음 에제 *functions.json* 파일에서는 트리거 및 바인딩을 하나씩 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="1f1ea-192">이 예제에서 함수는 `images` 컨테이너의 Blob 스토리지에 대한 변경에 의해 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="1f1ea-193">파일 정보가 전달되기 때문에 트리거가 바인딩의 역할도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="1f1ea-194">`images`라는 큐에 정보를 넣는 다른 바인딩이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="1f1ea-195">다음은 함수에 대한 C# 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="1f1ea-196">예제는 수정되었거나 Blob 스토리지에 업로드된 파일의 이름을 사용하고 나중에 처리할 수 있도록 큐에 배치하는 간단한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="1f1ea-197">트리거 및 바인딩의 전체 목록은 [Azure Functions 트리거 및 바인딩 개념](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="1f1ea-198">Proxy</span><span class="sxs-lookup"><span data-stu-id="1f1ea-198">Proxies</span></span>

<span data-ttu-id="1f1ea-199">프록시는 애플리케이션에 리디렉션 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="1f1ea-200">프록시는 엔드포인트를 노출하고 해당 엔드포인트를 다른 리소스에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="1f1ea-201">프록시를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-201">With proxies, you can:</span></span>

- <span data-ttu-id="1f1ea-202">들어오는 요청을 다른 엔드포인트로 다시 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-202">Reroute an incoming request to another endpoint.</span></span>
- <span data-ttu-id="1f1ea-203">들어오는 요청을 수정한 후 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-203">Modify the incoming request before it's passed along.</span></span>
- <span data-ttu-id="1f1ea-204">응답을 수정하거나 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-204">Modify or provide a response.</span></span>

<span data-ttu-id="1f1ea-205">프록시는 다음과 같은 시나리오에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-205">Proxies are used for scenarios such as:</span></span>

- <span data-ttu-id="1f1ea-206">URL을 단순화, 단축 또는 변경</span><span class="sxs-lookup"><span data-stu-id="1f1ea-206">Simplifying, shortening, or changing the URL.</span></span>
- <span data-ttu-id="1f1ea-207">여러 백 엔드 서비스에 일관된 API 접두사를 제공</span><span class="sxs-lookup"><span data-stu-id="1f1ea-207">Providing a consistent API prefix to multiple back-end services.</span></span>
- <span data-ttu-id="1f1ea-208">개발 중인 엔드포인트에 대한 응답을 모의</span><span class="sxs-lookup"><span data-stu-id="1f1ea-208">Mocking a response to an endpoint being developed.</span></span>
- <span data-ttu-id="1f1ea-209">잘 알려진 엔드포인트에 정적 응답을 제공</span><span class="sxs-lookup"><span data-stu-id="1f1ea-209">Providing a static response to a well-known endpoint.</span></span>
- <span data-ttu-id="1f1ea-210">백 엔드를 이동하거나 마이그레이션하는 동안 API 엔드포인트를 일관되게 유지</span><span class="sxs-lookup"><span data-stu-id="1f1ea-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="1f1ea-211">프록시는 JSON 정의로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="1f1ea-212">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-212">Here is an example:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

<span data-ttu-id="1f1ea-213">`Domain Redirect` 프록시는 약식 경로를 사용하여 더 긴 함수 리소스에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="1f1ea-214">변환은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="1f1ea-215">`Root` 프록시는 루트 URL(`https://--shorturl--/`)로 전송된 모든 항목을 가져와서 설명서 사이트로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="1f1ea-216">프록시를 사용하는 예제는 다음 동영상에 나와 있습니다. [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span><span class="sxs-lookup"><span data-stu-id="1f1ea-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="1f1ea-217">실시간으로 로컬 SQL Server에서 실행되는 ASP.NET Core 애플리케이션이 Azure Cloud로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="1f1ea-218">프록시는 함수를 사용하기 위해 기존Web API 프로젝트를 리팩터링하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="1f1ea-219">프록시에 대 한 자세한 내용은 [Azure Functions 프록시 사용](https://docs.microsoft.com/azure/azure-functions/functions-proxies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f1ea-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1f1ea-220">[이전](azure-serverless-platform.md)
>[다음](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="1f1ea-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
