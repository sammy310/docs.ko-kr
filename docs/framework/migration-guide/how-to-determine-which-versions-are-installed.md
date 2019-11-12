---
title: '방법: 설치된 .NET Framework 버전 확인'
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: 748b5ea2b14abe2da0b84430461eb68a70ae268d
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73195227"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="fea67-102">방법: 설치된 .NET Framework 버전 확인</span><span class="sxs-lookup"><span data-stu-id="fea67-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="fea67-103">사용자는 자신의 컴퓨터에 여러 버전의 .NET Framework를 [설치](../install/index.md)하여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-103">Users can [install](../install/index.md) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="fea67-104">따라서 앱을 개발하거나 배포할 때는 사용자의 컴퓨터에 어떤 .NET Framework 버전이 설치되었는지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span>

<span data-ttu-id="fea67-105">.NET Framework는 각 버전으로 식별되는 다음과 같은 2개의 주요 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>

- <span data-ttu-id="fea67-106">앱의 기능을 제공하는 형식 및 리소스 컬렉션에 해당하는 어셈블리 집합.</span><span class="sxs-lookup"><span data-stu-id="fea67-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="fea67-107">.NET Framework와 어셈블리는 동일한 버전 번호를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-107">The .NET Framework and assemblies share the same version number.</span></span>

- <span data-ttu-id="fea67-108">앱 코드를 관리하고 실행하는 CLR(공용 언어 런타임).</span><span class="sxs-lookup"><span data-stu-id="fea67-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="fea67-109">CLR은 고유한 버전 번호로 식별됩니다([버전 및 종속성](versions-and-dependencies.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="fea67-109">The CLR is identified by its own version number (see [Versions and dependencies](versions-and-dependencies.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="fea67-110">새 .NET Framework 버전에서는 각각 이전 버전의 기능을 유지하며 새 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="fea67-111">여러 버전의 .NET Framework를 동시에 단일 컴퓨터에서 로드할 수 있습니다. 즉, 이전 버전을 제거하지 않고도 .NET Framework를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="fea67-112">사용 중인 애플리케이션이 특정 버전에 종속적일 수 있고 해당 버전을 제거하면 애플리케이션이 중단될 수 있으므로 컴퓨터에서 .NET Framework의 이전버전은 일반적으로 제거해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="fea67-113">.NET Framework 버전과 CLR 버전은 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-113">There is a difference between the .NET Framework version and the CLR version:</span></span>
>
> - <span data-ttu-id="fea67-114">.NET Framework의 버전은 .NET Framework 클래스 라이브러리를 구성하는 어셈블리 세트를 기반으로 정해집니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="fea67-115">예를 들어, .NET Framework 버전에는 4.5, 4.6.1, 4.7.2가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span>
> - <span data-ttu-id="fea67-116">CLR의 버전은 .NET Framework 애플리케이션이 실행되는 런타임을 기반으로 정해집니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="fea67-117">하나의 CLR 버전이 여러 개의.NET Framework 버전을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="fea67-118">예를들어, CLR 버전 4.0.30319.*xxxxx*는 .NET Framework 버전 4~4.5.2를 지원하고, *xxxxx*는 42000보다 작으며, CLR버전 4.0.30319.42000은 .NET Framework 4.6.에서 시작하는 .NET Framework 버전을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2, where *xxxxx* is less than 42000, and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span>
>
> <span data-ttu-id="fea67-119">자세한 내용은 [.NET Framework 버전 및 종속성](versions-and-dependencies.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fea67-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>

<span data-ttu-id="fea67-120">컴퓨터에 설치된 .NET Framework 버전 목록을 보려면 레지스트리에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-120">To get a list of the .NET Framework versions installed on a computer, you access the registry.</span></span> <span data-ttu-id="fea67-121">또는 레지스트리 편집기를 사용하여 레지스트리를 확인하거나 코드로 레지스트리를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-121">You can either use the Registry Editor to view the registry or use code to query it:</span></span>

- <span data-ttu-id="fea67-122">최신 .NET Framework 버전 찾기(4.5 이상):</span><span class="sxs-lookup"><span data-stu-id="fea67-122">Find newer .NET Framework versions (4.5 and later):</span></span>
  - [<span data-ttu-id="fea67-123">레지스트리 편집기를 사용하여 .NET Framework 버전 찾기</span><span class="sxs-lookup"><span data-stu-id="fea67-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)
  - [<span data-ttu-id="fea67-124">코드를 사용하여 .NET Framework 버전에 대한 레지스트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="fea67-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)
  - [<span data-ttu-id="fea67-125">PowerShell을 사용하여 .NET Framework 버전에 대한 레지스트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="fea67-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)
- <span data-ttu-id="fea67-126">이전 .NET Framework 버전 찾기(1&#8211;4):</span><span class="sxs-lookup"><span data-stu-id="fea67-126">Find older .NET Framework versions (1&#8211;4):</span></span>
  - [<span data-ttu-id="fea67-127">레지스트리 편집기를 사용하여 .NET Framework 버전 찾기</span><span class="sxs-lookup"><span data-stu-id="fea67-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
  - [<span data-ttu-id="fea67-128">코드를 사용하여 .NET Framework 버전에 대한 레지스트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="fea67-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)

<span data-ttu-id="fea67-129">컴퓨터에 설치된 CLR 버전의 목록을 보려면 도구 또는 코드를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="fea67-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>

- [<span data-ttu-id="fea67-130">Clrver 도구 사용</span><span class="sxs-lookup"><span data-stu-id="fea67-130">Use the Clrver tool</span></span>](#clr_a)
- [<span data-ttu-id="fea67-131">코드를 사용하여 Environment 클래스 쿼리</span><span class="sxs-lookup"><span data-stu-id="fea67-131">Use code to query the Environment class</span></span>](#clr_b)

<span data-ttu-id="fea67-132">.NET Framework의 버전별로 설치된 업데이트를 검색하는 방법에 대한 자세한 내용은 [방법: 설치된 .NET Framework 업데이트 확인](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="fea67-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span>

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="fea67-133">최신 .NET Framework 버전 찾기(4.5 이상)</span><span class="sxs-lookup"><span data-stu-id="fea67-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<a name="net_b"></a>

### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="fea67-134">레지스트리에서 .NET Framework 버전 4.5 이상 찾기</span><span class="sxs-lookup"><span data-stu-id="fea67-134">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="fea67-135">**시작** 메뉴에서 **실행**을 선택하고 *regedit*을 입력한 다음, **OK**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-135">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="fea67-136">regedit을 실행하려면 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-136">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="fea67-137">레지스트리 편집기에서 다음 하위 키를 엽니다. **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="fea67-137">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="fea67-138">**전체**하위 키가 없으면 .NET Framework 4.5 이상이 설치되어 있지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-138">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fea67-139">레지스트리의 **NET Framework Setup** 폴더는 마침표로 시작하지 ‘않습니다’. </span><span class="sxs-lookup"><span data-stu-id="fea67-139">The **NET Framework Setup** folder in the registry does *not* begin with a period.</span></span>

3. <span data-ttu-id="fea67-140">**릴리스**라는 DWORD 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-140">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="fea67-141">릴리스 DWORD가 있으면 컴퓨터에 .NET Framework 4.5 이상이 설치된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-141">If it exists, then you have .NET Framework 4.5 or later versions installed.</span></span> <span data-ttu-id="fea67-142">그 값은 특정 버전의 .NET Framework에 대응되는 릴리스 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-142">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="fea67-143">예를 들어, 다음 그림에서 **릴리스**항목은 *378389*로, 이것은 .NET Framework 4.5.의 릴리스 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-143">In the following figure, for example, the value of the **Release** entry is *378389*, which is the release key for .NET Framework 4.5.</span></span>

     <span data-ttu-id="fea67-144">![.NET Framework 4.5.에 대한 레지스트리 항목](./media/clr-installdir.png ".NET Framework 4.5.에 대한 레지스트리 항목")</span><span class="sxs-lookup"><span data-stu-id="fea67-144">![Registry entry for the .NET Framework 4.5](./media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="fea67-145">다음 표에는 .NET Framework 4.5 이상 버전의 각 운영 체제상의 **릴리스** DWORD가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-145">The following table lists the value of the **Release** DWORD on individual operating systems for .NET Framework 4.5 and later versions.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="fea67-146">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="fea67-146">.NET Framework version</span></span>|<span data-ttu-id="fea67-147">릴리스 DWORD의 값</span><span class="sxs-lookup"><span data-stu-id="fea67-147">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="fea67-148">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="fea67-148">.NET Framework 4.5</span></span>|<span data-ttu-id="fea67-149">모든 Windows 운영 체제: 378389</span><span class="sxs-lookup"><span data-stu-id="fea67-149">All Windows operating systems: 378389</span></span>|
|<span data-ttu-id="fea67-150">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="fea67-150">.NET Framework 4.5.1</span></span>|<span data-ttu-id="fea67-151">Windows 8.1 및 Windows Server 2012 R2: 378675</span><span class="sxs-lookup"><span data-stu-id="fea67-151">On Windows 8.1 and Windows Server 2012 R2: 378675</span></span><br /><span data-ttu-id="fea67-152">다른 모든 Windows 운영 체제: 378758</span><span class="sxs-lookup"><span data-stu-id="fea67-152">On all other Windows operating systems: 378758</span></span>|
|<span data-ttu-id="fea67-153">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="fea67-153">.NET Framework 4.5.2</span></span>|<span data-ttu-id="fea67-154">모든 Windows 운영 체제: 379893</span><span class="sxs-lookup"><span data-stu-id="fea67-154">All Windows operating systems: 379893</span></span>|
|<span data-ttu-id="fea67-155">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="fea67-155">.NET Framework 4.6</span></span>|<span data-ttu-id="fea67-156">Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="fea67-156">On Windows 10: 393295</span></span><br /><span data-ttu-id="fea67-157">다른 모든 Windows 운영 체제: 393297</span><span class="sxs-lookup"><span data-stu-id="fea67-157">On all other Windows operating systems: 393297</span></span>|
|<span data-ttu-id="fea67-158">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="fea67-158">.NET Framework 4.6.1</span></span>|<span data-ttu-id="fea67-159">Windows 10 11월 업데이트 운영 체제: 394254</span><span class="sxs-lookup"><span data-stu-id="fea67-159">On Windows 10 November Update systems: 394254</span></span><br /><span data-ttu-id="fea67-160">다른 모든 Windows 운영 체제(Windows 10 포함): 394271</span><span class="sxs-lookup"><span data-stu-id="fea67-160">On all other Windows operating systems (including Windows 10): 394271</span></span>|
|<span data-ttu-id="fea67-161">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="fea67-161">.NET Framework 4.6.2</span></span>|<span data-ttu-id="fea67-162">Windows 10 1주년 업데이트 및 Windows Server 2016: 394802</span><span class="sxs-lookup"><span data-stu-id="fea67-162">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><span data-ttu-id="fea67-163">다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 394806</span><span class="sxs-lookup"><span data-stu-id="fea67-163">On all other Windows operating systems (including other Windows 10 operating systems): 394806</span></span>|
|<span data-ttu-id="fea67-164">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="fea67-164">.NET Framework 4.7</span></span>|<span data-ttu-id="fea67-165">Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="fea67-165">On Windows 10 Creators Update: 460798</span></span><br /><span data-ttu-id="fea67-166">다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 460805</span><span class="sxs-lookup"><span data-stu-id="fea67-166">On all other Windows operating systems (including other Windows 10 operating systems): 460805</span></span>|
|<span data-ttu-id="fea67-167">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="fea67-167">.NET Framework 4.7.1</span></span>|<span data-ttu-id="fea67-168">Windows 10 Fall Creators Update 및 Windows Server, 버전 1709: 461308</span><span class="sxs-lookup"><span data-stu-id="fea67-168">On Windows 10 Fall Creators Update and Windows Server, version 1709: 461308</span></span><br/><span data-ttu-id="fea67-169">다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 461310</span><span class="sxs-lookup"><span data-stu-id="fea67-169">On all other Windows operating systems (including other Windows 10 operating systems): 461310</span></span>|
|<span data-ttu-id="fea67-170">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="fea67-170">.NET Framework 4.7.2</span></span>|<span data-ttu-id="fea67-171">Windows 10 2018년 4월 업데이트 및 Windows Server, 버전 1803: 461808</span><span class="sxs-lookup"><span data-stu-id="fea67-171">On Windows 10 April 2018 Update and Windows Server, version 1803: 461808</span></span><br/><span data-ttu-id="fea67-172">Windows 10 2018년 4월 업데이트 및 Windows Server, 버전 1803 이외의 모든 Windows 운영 체제: 461814</span><span class="sxs-lookup"><span data-stu-id="fea67-172">On all Windows operating systems other than Windows 10 April 2018 Update and Windows Server, version 1803: 461814</span></span>|
|<span data-ttu-id="fea67-173">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="fea67-173">.NET Framework 4.8</span></span>|<span data-ttu-id="fea67-174">Windows 10 2019년 5월 업데이트 및 Windows 10 2019년 11월 업데이트: 528040</span><span class="sxs-lookup"><span data-stu-id="fea67-174">On Windows 10 May 2019 Update and Windows 10 November 2019 Update: 528040</span></span><br/><span data-ttu-id="fea67-175">다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 528049</span><span class="sxs-lookup"><span data-stu-id="fea67-175">On all other Windows operating systems (including other Windows 10 operating systems): 528049</span></span>|

<span data-ttu-id="fea67-176">이 값은 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-176">You can use these values as follows:</span></span>

- <span data-ttu-id="fea67-177">특정 버전의 .NET Framework가 특정 버전의 Windows 운영 체제에 설치되어 있는지 여부를 확인하려면 **릴리스** DWORD 값이 표에 나열된 값과 ‘동일한지’ 테스트하세요. </span><span class="sxs-lookup"><span data-stu-id="fea67-177">To determine whether a specific version of the .NET Framework is installed on a particular version of the Windows operating system, test whether the **Release** DWORD value is *equal to* the value listed in the table.</span></span> <span data-ttu-id="fea67-178">예를 들어 .NET Framework 4.6이 Windows 10 시스템에 있는지 확인하려면 **릴리스** 값이 393295와 ‘같은지’ 테스트합니다. </span><span class="sxs-lookup"><span data-stu-id="fea67-178">For example, to determine whether .NET Framework 4.6 is present on a Windows 10 system, test for the a **Release** value that is *equal to* 393295.</span></span>

- <span data-ttu-id="fea67-179">최하 버전의 .NET Framework가 있는지 확인하려면 해당 버전에 대해 더 작은 **릴리스** DWORD 값을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="fea67-179">To determine whether a minimum version of the .NET Framework is present, use the smaller **RELEASE** DWORD value for that version.</span></span> <span data-ttu-id="fea67-180">예를 들어 애플리케이션이 .NET Framework 4.8 이상 버전에서 실행되는 경우 528040과 *같거나 이보다 큰* **릴리스** DWORD 값을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-180">For example, if your application runs under .NET Framework 4.8 or a later version, test for a **RELEASE** DWORD value that is *greater than or equal to* 528040.</span></span> <span data-ttu-id="fea67-181">각 .NET Framework 버전에 대한 최소 **릴리스** DWORD 값만 나열하는 표를 보려면 [.NET Framework 4.5 이상 버전에서 릴리스 DWORD의 최솟값](minimum-release-dword.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fea67-181">For a table that lists only the minimum **RELEASE** DWORD value for each .NET Framework version, see [The minimum values of the Release DWORD for .NET Framework 4.5 and later versions](minimum-release-dword.md).</span></span>

- <span data-ttu-id="fea67-182">여러 버전을 테스트하려면 최신 .NET Framework 버전의 더 작은 DWORD 값과 ‘같거나 이보다 큰’ 값을 테스트한 후 연속적인 각 이전 버전에 대해 더 작은 DWORD 값과 비교하세요. </span><span class="sxs-lookup"><span data-stu-id="fea67-182">To test for multiple versions, begin by testing for a value that is *greater than or equal to* the smaller DWORD value for the latest .NET Framework version, and then compare the value with the smaller DWORD value for each successive earlier version.</span></span> <span data-ttu-id="fea67-183">예를 들어 애플리케이션에 .NET Framework 4.7 이상이 필요하고 특정 버전의 .NET Framework를 확인하려는 경우 461808(또는 .NET Framework 4.7.2의 경우는 더 작은 DWORD 값)과 ‘같거나 이보다 큰’ **릴리스** DWORD 값을 테스트하여 시작합니다. </span><span class="sxs-lookup"><span data-stu-id="fea67-183">For example, if your application requires .NET Framework 4.7 or later and you want to determine the specific version of .NET Framework present, start by testing for a **RELEASE** DWORD value that is *great than or equal to* to 461808 (the smaller DWORD value for .NET Framework 4.7.2).</span></span> <span data-ttu-id="fea67-184">그런 다음, 이 **릴리스** DWORD 값을 이후의 각 .NET Framework 버전에 대한 더 작은 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-184">Then compare the **RELEASE** DWORD value with the smaller value for each later .NET Framework version.</span></span> <span data-ttu-id="fea67-185">각 .NET Framework 버전에 대한 최소 **릴리스** DWORD 값만 나열하는 표를 보려면 [.NET Framework 4.5 이상 버전에서 릴리스 DWORD의 최솟값](minimum-release-dword.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fea67-185">For a table that lists only the minimum **RELEASE** DWORD value for each .NET Framework version, see [The minimum values of the Release DWORD for .NET Framework 4.5 and later versions](minimum-release-dword.md).</span></span>

<a name="net_d"></a>

### <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="fea67-186">코드를 사용하여 .NET Framework 버전 4.5 이상 찾기</span><span class="sxs-lookup"><span data-stu-id="fea67-186">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="fea67-187"><xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType>와 <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType>메서드를 사용하여 Windows 레지스트리의**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** 하위 키에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-187">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

    <span data-ttu-id="fea67-188">**릴리스** DWORD 항목이**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** 하위 키에 있으면 .NET Framework 4.5 이상 버전이 컴퓨터에 설치된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-188">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span>

2. <span data-ttu-id="fea67-189">**릴리스** 항목값을 확인하여 설치된 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-189">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="fea67-190">이후 버전과의 호환성을 유지하려는 경우 버전의 값이 [.NET Framework 버전 표](#version_table)에 나와 있는 값 이상인지를 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-190">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="fea67-191">다음 예제에서는 레지스트리에서 **릴리스** 항목값을 확인하여 .NET Framework 4.5 이상 버전이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-191">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="fea67-192">이 예제에서는 버전을 확인하기 위한 권장된 방법을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-192">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="fea67-193">**릴리스**항목의 값이 알려진 릴리스 키의 값보다 *크거나 같은지* 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-193">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="fea67-194">최신 버전에서 가장 오래된 버전 순서대로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-194">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a>

### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="fea67-195">PowerShell을 사용하여 필요한 최소 .NET Framework 버전(4.5 이상) 확인</span><span class="sxs-lookup"><span data-stu-id="fea67-195">Check for a minimum-required .NET Framework version (4.5 and later) with PowerShell</span></span>

- <span data-ttu-id="fea67-196">PowerShell 명령을 사용하여 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** 하위 키의 **릴리스** 항목값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-196">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="fea67-197">다음 예제에서는 **릴리스** 항목 값을 확인하여 .NET Framework 4.6.2 이상이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-197">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="fea67-198">`True`설치된 경우 코드 반환, 설치되지 않은 경우 `False` 코드 반환.</span><span class="sxs-lookup"><span data-stu-id="fea67-198">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="fea67-199">다른 최소 필수 .NET Framework 버전을 확인하려면 예제의 *394802*를 [.NET Framework 버전 표](#version_table)의 **릴리스** 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-199">To check for a different minimum-required .NET Framework version, replace *394802* in these examples with a **Release** value from the [.NET Framework version table](#version_table).</span></span>

## <a name="find-older-net-framework-versions-182114"></a><span data-ttu-id="fea67-200">이전 .NET Framework 버전 찾기(1&#8211;4)</span><span class="sxs-lookup"><span data-stu-id="fea67-200">Find older .NET Framework versions (1&#8211;4)</span></span>

<a name="net_a"></a>

### <a name="find-net-framework-versions-182114-in-the-registry"></a><span data-ttu-id="fea67-201">레지스트리에서 .NET Framework 버전 1&#8211;4 찾기</span><span class="sxs-lookup"><span data-stu-id="fea67-201">Find .NET Framework versions 1&#8211;4 in the registry</span></span>

1. <span data-ttu-id="fea67-202">**시작** 메뉴에서 **실행**을 선택하고 *regedit*을 입력한 다음, **OK**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-202">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

    <span data-ttu-id="fea67-203">regedit을 실행하려면 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-203">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="fea67-204">레지스트리 편집기에서 다음 하위 키를 엽니다. **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span><span class="sxs-lookup"><span data-stu-id="fea67-204">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>

    - <span data-ttu-id="fea67-205">.NET Framework 버전 1.1~3.5의 경우, 각각 설치된 버전이 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** 하위 키 아래에 하위 키로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-205">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="fea67-206">예,**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="fea67-206">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="fea67-207">버전 번호는 버전 하위 키의 **Version** 항목에 값으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-207">The version number is stored as a value in the version subkey's **Version** entry.</span></span>

    - <span data-ttu-id="fea67-208">.NET Framework 4의 경우 **Version** 항목은 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** 하위 키 또는 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** 하위 키 아래에, 또는 두 하위 키 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-208">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fea67-209">레지스트리의**NET Framework Setup**폴더는 마침표로 시작하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-209">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="fea67-210">다음 그림은 .NET Framework 3.5의 하위 키와 **Version** 항목을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-210">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="fea67-211">![.NET Framework 3.5에 대한 레지스트리 항목](./media/net-4-and-earlier.png ".NET Framework 3.5 및 이전 버전")</span><span class="sxs-lookup"><span data-stu-id="fea67-211">![The registry entry for the .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a>

### <a name="find-net-framework-versions-182114-with-code"></a><span data-ttu-id="fea67-212">코드를 사용하여 .NET Framework 버전 1&#8211;4 찾기</span><span class="sxs-lookup"><span data-stu-id="fea67-212">Find .NET Framework versions 1&#8211;4 with code</span></span>

- <span data-ttu-id="fea67-213"><xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>클래스를 사용하여 Windows 레지스트리의**HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** 하위 키에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-213">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="fea67-214">다음 예제에서는 설치된 .NET Framework 1&#8211;4버전을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-214">The following example finds the .NET Framework 1&#8211;4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a><span data-ttu-id="fea67-215">CLR 버전 찾기</span><span class="sxs-lookup"><span data-stu-id="fea67-215">Find CLR versions</span></span>

<a name="clr_a"></a>

### <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="fea67-216">Clrver.exe를 사용하여 현재 CLR 버전 찾기</span><span class="sxs-lookup"><span data-stu-id="fea67-216">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="fea67-217">[CLR 버전 도구(Clrver.exe)](../tools/clrver-exe-clr-version-tool.md)를 사용하여 컴퓨터에 설치된 공용 언어 런타임의 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-217">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="fea67-218">[Visual Studio용 개발자 명령 프롬프트](../tools/developer-command-prompt-for-vs.md)을 입력 `clrver` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-218">From a [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), enter `clrver`.</span></span>

    <span data-ttu-id="fea67-219">샘플 출력:</span><span class="sxs-lookup"><span data-stu-id="fea67-219">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="fea67-220">Environment 클래스를 사용하여 현재 CLR 버전 찾기</span><span class="sxs-lookup"><span data-stu-id="fea67-220">Find the current CLR version with the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fea67-221">.NET Framework 4.5 이상의 경우 <xref:System.Environment.Version%2A?displayProperty=nameWithType>속성을 사용하여 런타임의 버전을 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-221">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="fea67-222">대신 코드로 [.NET Framework 버전 4.5 이상 찾기](#net_d)에 설명된 것처럼 레지스트리를 쿼리하십시오.</span><span class="sxs-lookup"><span data-stu-id="fea67-222">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="fea67-223"><xref:System.Version>개체를 검색하기 위해 <xref:System.Environment.Version?displayProperty=nameWithType>속성을 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-223">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span>

    <span data-ttu-id="fea67-224">반환된 `System.Version`개체는 현재 코드를 실행하는 런타임 버전을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-224">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="fea67-225">컴퓨터에 설치된 어셈블리 버전이나 다른 런타임 버전은 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-225">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="fea67-226">.NET Framework 버전 4, 4.5, 4.5.1 및 4.5.2의 경우 반환된 <xref:System.Version>개체 문자열 표현은 4.0.30319.*xxxxx* 형식이며, *xxxxx*는 42000보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-226">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*, where *xxxxx* is less than 42000.</span></span> <span data-ttu-id="fea67-227">.NET Framework 4.6 및 이후 버전의 경우 형식은 4.0.30319.42000입니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-227">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>

2. <span data-ttu-id="fea67-228">`Version`개체를 가져온 후, 다음과 같이 개체를 쿼리하십시오.</span><span class="sxs-lookup"><span data-stu-id="fea67-228">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="fea67-229">주 릴리스 식별자(예:버전 4.0의 경우 *4*)는 <xref:System.Version.Major%2A?displayProperty=nameWithType>속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-229">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="fea67-230">부 릴리스 식별자(예:버전 4.0의 경우 *0*)를 가져오고 <xref:System.Version.Minor%2A?displayProperty=nameWithType>속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-230">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="fea67-231">전체 버전 문자열(예를 들어*4.0.30319.18010*)에는 <xref:System.Version.ToString%2A?displayProperty=nameWithType>메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-231">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fea67-232">메서드는 코드를 실행 하는 런타임 버전을 반영하는 단일 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-232">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="fea67-233">이는 컴퓨터에 설치된 어셈블리 버전이나 다른 런타임 버전은 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-233">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>

<span data-ttu-id="fea67-234">다음 예제에서는 <xref:System.Environment.Version%2A?displayProperty=nameWithType>속성을 사용하여 CLR 버전 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fea67-234">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="fea67-235">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fea67-235">See also</span></span>

- [<span data-ttu-id="fea67-236">방법: 설치된 .NET Framework 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="fea67-236">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="fea67-237">개발자용 .NET Framework 설치</span><span class="sxs-lookup"><span data-stu-id="fea67-237">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="fea67-238">.NET Framework 버전 및 종속성</span><span class="sxs-lookup"><span data-stu-id="fea67-238">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
