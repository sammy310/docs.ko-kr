---
title: Azure Functions-서버 리스 앱
description: Azure functions는 여러 언어 (C#, JavaScript, Java)에서 서버 리스 기능을 제공 하 고 이벤트 기반 인스턴트 제공 하는 플랫폼 코드를 확장 하세요.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4febcc01eebf3efce3fc1eb42e19c2ec6c0baa52
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754224"
---
# <a name="azure-functions"></a><span data-ttu-id="59bb0-103">Azure Functions</span><span class="sxs-lookup"><span data-stu-id="59bb0-103">Azure Functions</span></span>

<span data-ttu-id="59bb0-104">Azure functions는 서버 리스 계산 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="59bb0-105">함수를 호출한를 *트리거* (예: HTTP 끝점 또는 타이머에 대 한 액세스) 하 고 블록의 코드 또는 비즈니스 논리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="59bb0-106">또한 지원 특수화 된 함수 *바인딩* 저장소 및 큐와 같은 리소스에 연결 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure functions 로고](./media/azure-functions-logo.png)

<span data-ttu-id="59bb0-108">Azure Functions 프레임 워크의 두 가지 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="59bb0-109">레거시 버전을 전체.NET Framework를 지원 하 고 새 런타임 플랫폼 간.NET Core 응용 프로그램을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="59bb0-110">추가 언어 외에도 C# JavaScript 등 F#, 및 Java 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="59bb0-111">포털에서 만든 함수는 다양 한 스크립팅 구문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="59bb0-112">독립 실행형 프로젝트로 만든 함수는 전체 플랫폼 지원 및 기능을 사용 하 여 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="59bb0-113">자세한 내용은 [Azure Functions 설명서](https://docs.microsoft.com/azure/azure-functions)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="59bb0-114">Functions v1 및 v2</span><span class="sxs-lookup"><span data-stu-id="59bb0-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="59bb0-115">두 가지 버전의 Azure Functions 런타임: 1.x 및 2.x입니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="59bb0-116">버전 1.x는 일반 공급 (GA).</span><span class="sxs-lookup"><span data-stu-id="59bb0-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="59bb0-117">포털 또는 Windows 컴퓨터에서.NET 개발을 지원 하 고.NET Framework를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="59bb0-118">1.x 지원 C#, JavaScript 및 F#, Python, PHP, TypeScript, Batch, Bash 및 PowerShell에 대 한 실험적 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="59bb0-119">[버전 2.x는 이제 일반 공급도](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="59bb0-120">.NET Core를 활용 하 고 Windows, macOS 및 Linux 컴퓨터에서 플랫폼 간 개발을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="59bb0-121">2.x는 Java에 대 한 최상의 지원을 추가 하지만 실험적 언어 중 하나로 직접 지원 아직 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="59bb0-122">버전 2.x에 바인딩 독립 된 버전 관리 플랫폼에 타사 확장을 사용 하도록 설정 하는 새 바인딩 확장성 모델을 사용 하 여 및 더 효율적인 실행 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="59bb0-123">**1.x를 중인 알려진된 문제 [바인딩 리디렉션 지원](https://github.com/Azure/azure-functions-host/issues/992)합니다.**</span><span class="sxs-lookup"><span data-stu-id="59bb0-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="59bb0-124">이 문제는.NET 개발와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="59bb0-125">라이브러리에 런타임이 포함 된 라이브러리에서 다른 버전에 대 한 종속성을 사용 하 여 프로젝트에 영향 을지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="59bb0-126">기능 팀은 문제에 대 한 구체적인 진행 하기 위해 노력 했습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="59bb0-127">일반 공급으로 이동 하기 전에 팀에서 2.x에 바인딩 리디렉션을 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="59bb0-128">제안 된 수정 사항 및 해결 방법을 사용 하 여 공식 팀 문을 여기 제공 됩니다. [Azure Functions에서 어셈블리 확인](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="59bb0-129">자세한 내용은 [1.x와 2.x 비교](https://docs.microsoft.com/azure/azure-functions/functions-versions)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="59bb0-130">프로그래밍 언어 지원</span><span class="sxs-lookup"><span data-stu-id="59bb0-130">Programming language support</span></span>

<span data-ttu-id="59bb0-131">다음 언어를 지원 하거나 일반적 가용성 (GA)를 미리 보려면 실험적 또는 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="59bb0-132">언어</span><span class="sxs-lookup"><span data-stu-id="59bb0-132">Language</span></span>      |<span data-ttu-id="59bb0-133">1.x</span><span class="sxs-lookup"><span data-stu-id="59bb0-133">1.x</span></span>         |<span data-ttu-id="59bb0-134">2.x</span><span class="sxs-lookup"><span data-stu-id="59bb0-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="59bb0-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="59bb0-135">**C#**</span></span>        |<span data-ttu-id="59bb0-136">GA</span><span class="sxs-lookup"><span data-stu-id="59bb0-136">GA</span></span>          |<span data-ttu-id="59bb0-137">미리 보기</span><span class="sxs-lookup"><span data-stu-id="59bb0-137">Preview</span></span>  |
|<span data-ttu-id="59bb0-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="59bb0-138">**JavaScript**</span></span>|<span data-ttu-id="59bb0-139">GA</span><span class="sxs-lookup"><span data-stu-id="59bb0-139">GA</span></span>          |<span data-ttu-id="59bb0-140">미리 보기</span><span class="sxs-lookup"><span data-stu-id="59bb0-140">Preview</span></span>  |
|<span data-ttu-id="59bb0-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="59bb0-141">**F#**</span></span>        |<span data-ttu-id="59bb0-142">GA</span><span class="sxs-lookup"><span data-stu-id="59bb0-142">GA</span></span>          |         |
|<span data-ttu-id="59bb0-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="59bb0-143">**Java**</span></span>      |            |<span data-ttu-id="59bb0-144">미리 보기</span><span class="sxs-lookup"><span data-stu-id="59bb0-144">Preview</span></span>  |
|<span data-ttu-id="59bb0-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="59bb0-145">**Python**</span></span>    |<span data-ttu-id="59bb0-146">실험적</span><span class="sxs-lookup"><span data-stu-id="59bb0-146">Experimental</span></span>|         |
|<span data-ttu-id="59bb0-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="59bb0-147">**PHP**</span></span>       |<span data-ttu-id="59bb0-148">실험적</span><span class="sxs-lookup"><span data-stu-id="59bb0-148">Experimental</span></span>|         |
|<span data-ttu-id="59bb0-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="59bb0-149">**TypeScript**</span></span>|<span data-ttu-id="59bb0-150">실험적</span><span class="sxs-lookup"><span data-stu-id="59bb0-150">Experimental</span></span>|         |
|<span data-ttu-id="59bb0-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="59bb0-151">**Batch**</span></span>     |<span data-ttu-id="59bb0-152">실험적</span><span class="sxs-lookup"><span data-stu-id="59bb0-152">Experimental</span></span>|         |
|<span data-ttu-id="59bb0-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="59bb0-153">**Bash**</span></span>      |<span data-ttu-id="59bb0-154">실험적</span><span class="sxs-lookup"><span data-stu-id="59bb0-154">Experimental</span></span>|         |
|<span data-ttu-id="59bb0-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="59bb0-155">**PowerShell**</span></span>|<span data-ttu-id="59bb0-156">실험적</span><span class="sxs-lookup"><span data-stu-id="59bb0-156">Experimental</span></span>|         |

<span data-ttu-id="59bb0-157">자세한 내용은 [지원 되는 언어](https://docs.microsoft.com/azure/azure-functions/supported-languages)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="59bb0-158">App service 계획</span><span class="sxs-lookup"><span data-stu-id="59bb0-158">App service plans</span></span>

<span data-ttu-id="59bb0-159">함수에서 지원 되는 *app service 계획*합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="59bb0-160">계획을 함수 앱에서 사용 하는 리소스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="59bb0-161">지역에 계획을 할당 하, 크기와 사용 되며 가격 책정 계층을 선택 하는 가상 머신의 수를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="59bb0-162">True 이면 서버 리스 방식, 함수 앱 사용할 수는 **소비** 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="59bb0-163">소비 계획에는 백 엔드 부하에 따라 자동으로 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="59bb0-164">자세한 내용은 [App service 계획](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="59bb0-165">첫 번째 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="59bb0-165">Create your first function</span></span>

<span data-ttu-id="59bb0-166">세 가지 일반적인 함수 앱을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-166">There are three common ways you can create function apps.</span></span>

* <span data-ttu-id="59bb0-167">포털에서 함수를 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-167">Script functions in the portal.</span></span>
* <span data-ttu-id="59bb0-168">Azure 명령줄 인터페이스 (CLI)를 사용 하는 데 필요한 리소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
* <span data-ttu-id="59bb0-169">즐겨 찾는 IDE를 사용 하 여 로컬로 함수를 빌드하고 Azure에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="59bb0-170">포털에서 스크립팅된 함수를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [Azure portal에서 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="59bb0-171">Azure CLI에서 빌드 참조 [Azure CLI를 사용 하 여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="59bb0-172">Visual Studio에서 함수를 만들기, 참조 [Visual Studio를 사용 하 여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="59bb0-173">트리거 및 바인딩 이해</span><span class="sxs-lookup"><span data-stu-id="59bb0-173">Understand triggers and bindings</span></span>

<span data-ttu-id="59bb0-174">함수에서 호출 되는 *트리거* 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="59bb0-175">함수를 호출 하는 것 외에도 특정 트리거 역할도 바인딩.</span><span class="sxs-lookup"><span data-stu-id="59bb0-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="59bb0-176">또한 트리거 외에도 여러 바인딩을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="59bb0-177">*바인딩* 데이터 코드를 연결 하는 선언적 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="59bb0-178">이러한 (입력)에 전달 될 수 또는 데이터 (출력)를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="59bb0-179">트리거 및 바인딩 함수를 사용 하기 쉽게 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="59bb0-180">바인딩은 시스템 연결 데이터베이스 또는 파일을 수동으로 만드는 오버 헤드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="59bb0-181">특별 한에 포함 된 모든 바인딩에 대 한 필요한 정보의 *functions.json* 스크립트에 대 한 파일 또는 코드에서 특성을 사용 하 여 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="59bb0-182">일부 공통 트리거는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-182">Some common triggers include:</span></span>

* <span data-ttu-id="59bb0-183">Blob Storage: 파일 또는 폴더를 업로드 하거나 저장소에서 변경할 때 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
* <span data-ttu-id="59bb0-184">HTTP: REST API와 같은 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-184">HTTP: invoke your function like a REST API.</span></span>
* <span data-ttu-id="59bb0-185">큐: 큐에 항목이 존재 하는 경우 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-185">Queue: invoke your function when items exist in a queue.</span></span>
* <span data-ttu-id="59bb0-186">타이머: 일반 주기로 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="59bb0-187">바인딩의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-187">Examples of bindings include:</span></span>

* <span data-ttu-id="59bb0-188">Cosmos Db: 쉽게 로드 하거나 파일을 저장 하려면 데이터베이스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-188">CosmosDB: easily connect to the database to load or save files.</span></span>
* <span data-ttu-id="59bb0-189">Table Storage: 함수 앱에서 키/값 저장소를 사용 하 여 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-189">Table Storage: work with key/value storage from your function app.</span></span>
* <span data-ttu-id="59bb0-190">Queue Storage:는 쉽게 큐에서 항목을 검색 하거나 큐에 새 항목을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="59bb0-191">다음 예제에서는 *functions.json* 파일 트리거 및 바인딩을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="59bb0-192">이 예제에서는 함수는 blob 저장소에 변경에 따라 트리거되는 `images` 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="59bb0-193">트리거 바인딩을 역할도 하므로, 파일에 대 한 정보를 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="59bb0-194">다른 바인딩 이라는 큐에 정보를 설정 하기 위해 존재 `images`합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="59bb0-195">C# 스크립트 함수에는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="59bb0-196">예제는 수정 된 또는 blob storage에 업로드 및 나중에 처리 큐에 배치 하는 파일의 이름을 사용 하는 간단한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="59bb0-197">트리거 및 바인딩의 전체 목록을 참조 하세요 [Azure Functions 트리거 및 바인딩 개념](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="59bb0-198">Proxy</span><span class="sxs-lookup"><span data-stu-id="59bb0-198">Proxies</span></span>

<span data-ttu-id="59bb0-199">프록시 응용 프로그램에 대 한 리디렉션 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="59bb0-200">프록시 끝점을 노출 하 고 다른 리소스에 해당 끝점을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="59bb0-201">프록시를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-201">With proxies, you can:</span></span>

* <span data-ttu-id="59bb0-202">다른 끝점으로 들어오는 요청을 다시 라우팅하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-202">Reroute an incoming request to another endpoint.</span></span>
* <span data-ttu-id="59bb0-203">따라 전달 되기 전에 들어오는 요청을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-203">Modify the incoming request before it's passed along.</span></span>
* <span data-ttu-id="59bb0-204">수정 하거나 응답을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-204">Modify or provide a response.</span></span>

<span data-ttu-id="59bb0-205">프록시는와 같은 시나리오에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-205">Proxies are used for scenarios such as:</span></span>

* <span data-ttu-id="59bb0-206">간소화, 단축, 또는 URL을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-206">Simplifying, shortening, or changing the URL.</span></span>
* <span data-ttu-id="59bb0-207">여러 백 엔드 서비스에 일관 된 API 접두사를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-207">Providing a consistent API prefix to multiple back-end services.</span></span>
* <span data-ttu-id="59bb0-208">개발 중인 끝점에 대 한 응답 모의 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-208">Mocking a response to an endpoint being developed.</span></span>
* <span data-ttu-id="59bb0-209">잘 알려진 끝점에 대 한 정적 응답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-209">Providing a static response to a well-known endpoint.</span></span>
* <span data-ttu-id="59bb0-210">백 엔드를 이동 또는 마이그레이션 하는 동안 API 끝점의 일관성 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="59bb0-211">프록시는 JSON 정의로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="59bb0-212">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-212">Here is an example:</span></span>

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

<span data-ttu-id="59bb0-213">`Domain Redirect` 프록시 축약된 경로 가져오고 더 함수 리소스에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="59bb0-214">변환은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="59bb0-215">합니다 `Root` 프록시는 루트 URL로 전송 하는 아무 것도 (`https://--shorturl--/`) 설명서 사이트에 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="59bb0-216">비디오에서 프록시를 사용 하는 예가 나와 있습니다 [Azure: 앱 서버 리스 Azure Functions를 사용 하 여 클라우드로 가져올](https://channel9.msdn.com/events/Connect/2017/E102)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="59bb0-217">실시간으로 로컬 SQL Server에서 실행 되는 ASP.NET Core 응용 프로그램은 Azure 클라우드로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="59bb0-218">프록시는 함수를 사용 하도록 기존 Web API 프로젝트를 리팩터링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="59bb0-219">프록시에 대 한 자세한 내용은 참조 하세요. [Azure Functions 프록시 사용](https://docs.microsoft.com/azure/azure-functions/functions-proxies)합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb0-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="59bb0-220">[이전](azure-serverless-platform.md)
>[다음](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="59bb0-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
