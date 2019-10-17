---
title: Azure Functions 서버 리스 앱
description: Azure 함수는 여러 언어 (C#, JavaScript, Java) 및 플랫폼에서 서버 리스 기능을 제공 하 여 이벤트 중심의 즉시 확장 코드를 제공 합니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5e8187b3752a0f0d0bcf8e15f2ce440dc5a64e45
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522873"
---
# <a name="azure-functions"></a><span data-ttu-id="d82bf-103">Azure Functions</span><span class="sxs-lookup"><span data-stu-id="d82bf-103">Azure Functions</span></span>

<span data-ttu-id="d82bf-104">Azure 함수는 서버를 사용 하지 않는 계산 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="d82bf-105">함수는 *트리거* (예: HTTP 끝점 또는 타이머에 대 한 액세스)에 의해 호출 되며, 코드 블록 또는 비즈니스 논리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="d82bf-106">또한 함수는 저장소 및 큐와 같은 리소스에 연결 하는 특수 *바인딩을* 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure 함수 로고](./media/azure-functions-logo.png)

<span data-ttu-id="d82bf-108">Azure Functions 프레임 워크에는 두 가지 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="d82bf-109">레거시 버전은 전체 .NET Framework을 지원 하 고 새 런타임은 플랫폼 간 .NET Core 응용 프로그램을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="d82bf-110">JavaScript, F#및 C# Java와 같은 추가 언어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="d82bf-111">포털에서 만든 함수는 풍부한 스크립팅 구문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="d82bf-112">독립 실행형 프로젝트로 만들어진 함수는 전체 플랫폼 지원 및 기능을 사용 하 여 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="d82bf-113">자세한 내용은 [Azure Functions 설명서](https://docs.microsoft.com/azure/azure-functions)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82bf-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="d82bf-114">함수 v1 및 v2</span><span class="sxs-lookup"><span data-stu-id="d82bf-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="d82bf-115">Azure Functions 런타임의 두 가지 버전은 1.x 및 2.x입니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="d82bf-116">버전 1.x를 일반적으로 사용할 수 있습니다 (GA).</span><span class="sxs-lookup"><span data-stu-id="d82bf-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="d82bf-117">포털 또는 Windows 컴퓨터에서 .NET 개발을 지원 하 고 .NET Framework를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="d82bf-118">1.x는 Python C#, PHP, TypeScript F#, Batch, Bash 및 PowerShell에 대 한 실험적 지원으로, JavaScript 및를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="d82bf-119">[버전 2.x는 이제 일반적으로 사용할 수](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/)있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="d82bf-120">.NET Core를 활용 하 고 Windows, macOS 및 Linux 컴퓨터에서 플랫폼 간 개발을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="d82bf-121">2.x는 Java에 대 한 첫 번째 클래스 지원을 추가 하지만 실험적 언어를 아직 직접 지원 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="d82bf-122">버전 2.x는 플랫폼에 대 한 타사 확장, 바인딩의 독립적인 버전 관리 및 보다 간소화 된 실행 환경을 가능 하 게 하는 새로운 바인딩 확장성 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="d82bf-123">**바인딩과 관련 된 알려진 문제는 [바인딩 리디렉션 지원](https://github.com/Azure/azure-functions-host/issues/992)입니다.**</span><span class="sxs-lookup"><span data-stu-id="d82bf-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="d82bf-124">이 문제는 .NET 개발과 관련 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="d82bf-125">런타임에 포함 된 라이브러리와 다른 버전의 라이브러리에 대 한 종속성이 있는 프로젝트는 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="d82bf-126">함수 팀은 문제를 구체적으로 진행 하기 위해 최선을 다하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="d82bf-127">팀은 일반 공급으로 전환 하기 전에 2.x의 바인딩 리디렉션을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="d82bf-128">제안 된 수정 사항 및 해결 방법을 제공 하는 공식 팀 명세서는 [Azure Functions의 어셈블리 해상도에서](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions)제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="d82bf-129">자세한 내용은 1.x 및 2.x [비교](https://docs.microsoft.com/azure/azure-functions/functions-versions)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82bf-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="d82bf-130">프로그래밍 언어 지원</span><span class="sxs-lookup"><span data-stu-id="d82bf-130">Programming language support</span></span>

<span data-ttu-id="d82bf-131">GA (일반 공급), 미리 보기 또는 실험적에서 지원 되는 언어는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="d82bf-132">언어</span><span class="sxs-lookup"><span data-stu-id="d82bf-132">Language</span></span>      |<span data-ttu-id="d82bf-133">1.x</span><span class="sxs-lookup"><span data-stu-id="d82bf-133">1.x</span></span>         |<span data-ttu-id="d82bf-134">2.x</span><span class="sxs-lookup"><span data-stu-id="d82bf-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="d82bf-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="d82bf-135">**C#**</span></span>        |<span data-ttu-id="d82bf-136">GA</span><span class="sxs-lookup"><span data-stu-id="d82bf-136">GA</span></span>          |<span data-ttu-id="d82bf-137">미리 보기</span><span class="sxs-lookup"><span data-stu-id="d82bf-137">Preview</span></span>  |
|<span data-ttu-id="d82bf-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="d82bf-138">**JavaScript**</span></span>|<span data-ttu-id="d82bf-139">GA</span><span class="sxs-lookup"><span data-stu-id="d82bf-139">GA</span></span>          |<span data-ttu-id="d82bf-140">미리 보기</span><span class="sxs-lookup"><span data-stu-id="d82bf-140">Preview</span></span>  |
|<span data-ttu-id="d82bf-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="d82bf-141">**F#**</span></span>        |<span data-ttu-id="d82bf-142">GA</span><span class="sxs-lookup"><span data-stu-id="d82bf-142">GA</span></span>          |         |
|<span data-ttu-id="d82bf-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="d82bf-143">**Java**</span></span>      |            |<span data-ttu-id="d82bf-144">미리 보기</span><span class="sxs-lookup"><span data-stu-id="d82bf-144">Preview</span></span>  |
|<span data-ttu-id="d82bf-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="d82bf-145">**Python**</span></span>    |<span data-ttu-id="d82bf-146">실험적</span><span class="sxs-lookup"><span data-stu-id="d82bf-146">Experimental</span></span>|         |
|<span data-ttu-id="d82bf-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="d82bf-147">**PHP**</span></span>       |<span data-ttu-id="d82bf-148">실험적</span><span class="sxs-lookup"><span data-stu-id="d82bf-148">Experimental</span></span>|         |
|<span data-ttu-id="d82bf-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="d82bf-149">**TypeScript**</span></span>|<span data-ttu-id="d82bf-150">실험적</span><span class="sxs-lookup"><span data-stu-id="d82bf-150">Experimental</span></span>|         |
|<span data-ttu-id="d82bf-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="d82bf-151">**Batch**</span></span>     |<span data-ttu-id="d82bf-152">실험적</span><span class="sxs-lookup"><span data-stu-id="d82bf-152">Experimental</span></span>|         |
|<span data-ttu-id="d82bf-153">**Bug**</span><span class="sxs-lookup"><span data-stu-id="d82bf-153">**Bash**</span></span>      |<span data-ttu-id="d82bf-154">실험적</span><span class="sxs-lookup"><span data-stu-id="d82bf-154">Experimental</span></span>|         |
|<span data-ttu-id="d82bf-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d82bf-155">**PowerShell**</span></span>|<span data-ttu-id="d82bf-156">실험적</span><span class="sxs-lookup"><span data-stu-id="d82bf-156">Experimental</span></span>|         |

<span data-ttu-id="d82bf-157">자세한 내용은 [지원 되는 언어](https://docs.microsoft.com/azure/azure-functions/supported-languages)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82bf-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="d82bf-158">App service 계획</span><span class="sxs-lookup"><span data-stu-id="d82bf-158">App service plans</span></span>

<span data-ttu-id="d82bf-159">함수는 *app service 계획*에 의해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="d82bf-160">계획은 함수 앱에서 사용 하는 리소스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="d82bf-161">지역에 계획을 할당 하 고, 사용 되는 가상 머신의 크기와 수를 결정 하 고, 가격 책정 계층을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="d82bf-162">서버를 사용 하지 않는 방식의 경우 함수 앱은 **소비** 계획을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="d82bf-163">소비 계획은 부하에 따라 백 엔드를 자동으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="d82bf-164">자세한 내용은 [App service 계획](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82bf-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="d82bf-165">첫 번째 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="d82bf-165">Create your first function</span></span>

<span data-ttu-id="d82bf-166">세 가지 일반적인 방법으로 함수 앱을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-166">There are three common ways you can create function apps.</span></span>

- <span data-ttu-id="d82bf-167">포털에서 함수를 스크립팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-167">Script functions in the portal.</span></span>
- <span data-ttu-id="d82bf-168">Azure CLI (명령줄 인터페이스)를 사용 하 여 필요한 리소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
- <span data-ttu-id="d82bf-169">즐겨 사용 하는 IDE를 사용 하 여 함수를 로컬로 빌드하고 Azure에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="d82bf-170">포털에서 스크립팅된 함수를 만드는 방법에 대 한 자세한 내용은 [Azure Portal에서 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82bf-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="d82bf-171">Azure CLI에서 빌드하려면 [Azure CLI를 사용 하 여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82bf-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="d82bf-172">Visual Studio에서 함수를 만들려면 [Visual studio를 사용 하 여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82bf-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="d82bf-173">트리거 및 바인딩 이해</span><span class="sxs-lookup"><span data-stu-id="d82bf-173">Understand triggers and bindings</span></span>

<span data-ttu-id="d82bf-174">함수는 *트리거에서* 호출 하며 정확히 하나의 함수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="d82bf-175">함수를 호출 하는 것 외에도 특정 트리거는 바인딩으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="d82bf-176">트리거와 함께 여러 바인딩을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="d82bf-177">*바인딩은* 데이터를 코드에 연결 하는 선언적 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="d82bf-178">이러한 데이터는 (입력)에 전달 되거나 데이터를 받을 수 있습니다 (출력).</span><span class="sxs-lookup"><span data-stu-id="d82bf-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="d82bf-179">트리거 및 바인딩을 사용 하면 함수를 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="d82bf-180">바인딩은 데이터베이스 또는 파일 시스템 연결을 수동으로 만드는 오버 헤드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="d82bf-181">바인딩에 필요한 모든 정보는 스크립트를 위한 json 파일 또는 코드에서 특성으로 선언 된 특수 한 함수에 포함 되어 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="d82bf-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="d82bf-182">몇 가지 일반적인 트리거는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-182">Some common triggers include:</span></span>

- <span data-ttu-id="d82bf-183">Blob Storage: 파일이 나 폴더가 저장소에서 업로드 또는 변경 될 때 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
- <span data-ttu-id="d82bf-184">HTTP: REST API 처럼 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-184">HTTP: invoke your function like a REST API.</span></span>
- <span data-ttu-id="d82bf-185">Queue: 큐에 항목이 있을 때 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-185">Queue: invoke your function when items exist in a queue.</span></span>
- <span data-ttu-id="d82bf-186">Timer: 일반 흐름에서 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="d82bf-187">바인딩의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-187">Examples of bindings include:</span></span>

- <span data-ttu-id="d82bf-188">CosmosDB: 데이터베이스에 쉽게 연결 하 여 파일을 로드 하거나 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-188">CosmosDB: easily connect to the database to load or save files.</span></span>
- <span data-ttu-id="d82bf-189">Table Storage: 함수 앱에서 키/값 저장소로 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-189">Table Storage: work with key/value storage from your function app.</span></span>
- <span data-ttu-id="d82bf-190">Queue Storage: 큐에서 항목을 쉽게 검색 하거나 새 항목을 큐에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="d82bf-191">다음 예의 *함수 json* 파일은 트리거와 바인딩을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="d82bf-192">이 예제에서 함수는 `images` 컨테이너의 blob 저장소에 대 한 변경 내용에 의해 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="d82bf-193">파일에 대 한 정보는 전달 되기 때문에 트리거도 바인딩 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="d82bf-194">@No__t-0 이라는 큐에 정보를 넣는 다른 바인딩이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="d82bf-195">다음은 함수 C# 에 대 한 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="d82bf-196">예제는 blob 저장소에 수정 또는 업로드 된 파일의 이름을 사용 하 고 나중에 처리할 수 있도록 큐에 배치 하는 간단한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="d82bf-197">트리거와 바인딩의 전체 목록은 [Azure Functions 트리거 및 바인딩 개념](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82bf-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="d82bf-198">Proxy</span><span class="sxs-lookup"><span data-stu-id="d82bf-198">Proxies</span></span>

<span data-ttu-id="d82bf-199">프록시는 응용 프로그램에 대 한 리디렉션 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="d82bf-200">프록시는 끝점을 노출 하 고 해당 끝점을 다른 리소스에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="d82bf-201">프록시를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-201">With proxies, you can:</span></span>

- <span data-ttu-id="d82bf-202">들어오는 요청을 다른 끝점으로 경로 바꾸기</span><span class="sxs-lookup"><span data-stu-id="d82bf-202">Reroute an incoming request to another endpoint.</span></span>
- <span data-ttu-id="d82bf-203">들어오는 요청을 전달 하기 전에 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-203">Modify the incoming request before it's passed along.</span></span>
- <span data-ttu-id="d82bf-204">응답을 수정 하거나 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-204">Modify or provide a response.</span></span>

<span data-ttu-id="d82bf-205">프록시는 다음과 같은 시나리오에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-205">Proxies are used for scenarios such as:</span></span>

- <span data-ttu-id="d82bf-206">URL을 단순화, 단축 또는 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-206">Simplifying, shortening, or changing the URL.</span></span>
- <span data-ttu-id="d82bf-207">여러 백 엔드 서비스에 일관 된 API 접두사 제공</span><span class="sxs-lookup"><span data-stu-id="d82bf-207">Providing a consistent API prefix to multiple back-end services.</span></span>
- <span data-ttu-id="d82bf-208">개발 중인 끝점에 대 한 응답을 모의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-208">Mocking a response to an endpoint being developed.</span></span>
- <span data-ttu-id="d82bf-209">잘 알려진 끝점에 정적 응답을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-209">Providing a static response to a well-known endpoint.</span></span>
- <span data-ttu-id="d82bf-210">백 엔드를 이동 하거나 마이그레이션하는 동안 API 끝점을 일관 되 게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="d82bf-211">프록시는 JSON 정의로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="d82bf-212">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-212">Here is an example:</span></span>

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

<span data-ttu-id="d82bf-213">@No__t-0 프록시는 약식 경로를 사용 하 여 더 긴 함수 리소스에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="d82bf-214">변환은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="d82bf-215">@No__t-0 프록시는 루트 URL (`https://--shorturl--/`)로 전송 된 모든 항목을 가져와서 설명서 사이트로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="d82bf-216">프록시 사용에 대 한 예제는 [Azure: 서버 리스 Azure Functions를 사용 하 여 앱을 클라우드로 가져오기](https://channel9.msdn.com/events/Connect/2017/E102)에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="d82bf-217">실시간으로 로컬 SQL Server에서 실행 되는 ASP.NET Core 응용 프로그램은 Azure 클라우드로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="d82bf-218">프록시는 함수를 사용 하기 위해 기존 Web API 프로젝트를 리팩터링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82bf-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="d82bf-219">프록시에 대 한 자세한 내용은 [Azure Functions 프록시 사용](https://docs.microsoft.com/azure/azure-functions/functions-proxies)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82bf-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d82bf-220">[이전](azure-serverless-platform.md)
>[다음](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="d82bf-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
