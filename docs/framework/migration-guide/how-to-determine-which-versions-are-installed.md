---
title: 설치된 .NET Framework 버전 확인
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: b860aac01780acb67c53e822eff478b78198996b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738197"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="23492-102">방법: 설치된 .NET Framework 버전 확인</span><span class="sxs-lookup"><span data-stu-id="23492-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="23492-103">사용자는 자신의 컴퓨터에 여러 버전의 .NET Framework를 [설치](../install/index.md)하여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-103">Users can [install](../install/index.md) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="23492-104">따라서 앱을 개발하거나 배포할 때는 사용자의 컴퓨터에 어떤 .NET Framework 버전이 설치되었는지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span>

<span data-ttu-id="23492-105">.NET Framework는 각 버전으로 식별되는 다음과 같은 2개의 주요 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="23492-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>

- <span data-ttu-id="23492-106">앱의 기능을 제공하는 형식 및 리소스 컬렉션에 해당하는 어셈블리 집합.</span><span class="sxs-lookup"><span data-stu-id="23492-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="23492-107">.NET Framework와 어셈블리는 동일한 버전 번호를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-107">The .NET Framework and assemblies share the same version number.</span></span>

- <span data-ttu-id="23492-108">앱 코드를 관리하고 실행하는 CLR(공용 언어 런타임).</span><span class="sxs-lookup"><span data-stu-id="23492-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="23492-109">CLR은 고유한 버전 번호로 식별됩니다([버전 및 종속성](versions-and-dependencies.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="23492-109">The CLR is identified by its own version number (see [Versions and dependencies](versions-and-dependencies.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="23492-110">새 .NET Framework 버전에서는 각각 이전 버전의 기능을 유지하며 새 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="23492-111">여러 버전의 .NET Framework를 동시에 단일 컴퓨터에서 로드할 수 있습니다. 즉, 이전 버전을 제거하지 않고도 .NET Framework를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="23492-112">사용 중인 애플리케이션이 특정 버전에 종속적일 수 있고 해당 버전을 제거하면 애플리케이션이 중단될 수 있으므로 컴퓨터에서 .NET Framework의 이전버전은 일반적으로 제거해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23492-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="23492-113">.NET Framework 버전과 CLR 버전은 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="23492-113">There is a difference between the .NET Framework version and the CLR version:</span></span>
>
> - <span data-ttu-id="23492-114">.NET Framework의 버전은 .NET Framework 클래스 라이브러리를 구성하는 어셈블리 세트를 기반으로 정해집니다.</span><span class="sxs-lookup"><span data-stu-id="23492-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="23492-115">예를 들어, .NET Framework 버전에는 4.5, 4.6.1, 4.7.2가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span>
> - <span data-ttu-id="23492-116">CLR의 버전은 .NET Framework 애플리케이션이 실행되는 런타임을 기반으로 정해집니다.</span><span class="sxs-lookup"><span data-stu-id="23492-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="23492-117">하나의 CLR 버전이 여러 개의.NET Framework 버전을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="23492-118">예를들어, CLR 버전 4.0.30319.*xxxxx*는 .NET Framework 버전 4~4.5.2를 지원하고, *xxxxx*는 42000보다 작으며, CLR버전 4.0.30319.42000은 .NET Framework 4.6.에서 시작하는 .NET Framework 버전을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2, where *xxxxx* is less than 42000, and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span>
>
> <span data-ttu-id="23492-119">자세한 내용은 [.NET Framework 버전 및 종속성](versions-and-dependencies.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="23492-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>

<span data-ttu-id="23492-120">레지스트리에는 컴퓨터에 설치된 .NET Framework 버전 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-120">The registry contains a list of the .NET Framework versions installed on a computer.</span></span> <span data-ttu-id="23492-121">레지스트리 편집기를 사용하여 레지스트리를 확인하거나 코드로 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-121">You can either use the Registry Editor to view the registry or query it with code:</span></span>

- <span data-ttu-id="23492-122">최신 .NET Framework 버전 찾기(4.5 이상):</span><span class="sxs-lookup"><span data-stu-id="23492-122">Find newer .NET Framework versions (4.5 and later):</span></span>

  - [<span data-ttu-id="23492-123">레지스트리 편집기를 사용하여 .NET Framework 버전 찾기</span><span class="sxs-lookup"><span data-stu-id="23492-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)
  - [<span data-ttu-id="23492-124">코드를 사용하여 .NET Framework 버전에 대한 레지스트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="23492-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)
  - [<span data-ttu-id="23492-125">PowerShell을 사용하여 .NET Framework 버전에 대한 레지스트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="23492-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)

- <span data-ttu-id="23492-126">이전 .NET Framework 버전 찾기(1~4):</span><span class="sxs-lookup"><span data-stu-id="23492-126">Find older .NET Framework versions (1 through 4):</span></span>

  - [<span data-ttu-id="23492-127">레지스트리 편집기를 사용하여 .NET Framework 버전 찾기</span><span class="sxs-lookup"><span data-stu-id="23492-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
  - [<span data-ttu-id="23492-128">코드를 사용하여 .NET Framework 버전에 대한 레지스트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="23492-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)

<span data-ttu-id="23492-129">컴퓨터에 설치된 CLR 버전의 목록을 보려면 도구 또는 코드를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="23492-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>

- [<span data-ttu-id="23492-130">Clrver 도구 사용</span><span class="sxs-lookup"><span data-stu-id="23492-130">Use the Clrver tool</span></span>](#clr_a)
- [<span data-ttu-id="23492-131">코드를 사용하여 Environment 클래스 쿼리</span><span class="sxs-lookup"><span data-stu-id="23492-131">Use code to query the Environment class</span></span>](#clr_b)

<span data-ttu-id="23492-132">.NET Framework의 버전별로 설치된 업데이트를 검색하는 방법에 대한 자세한 내용은 [방법: 설치된 .NET Framework 업데이트 확인](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="23492-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span>

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="23492-133">최신 .NET Framework 버전 찾기(4.5 이상)</span><span class="sxs-lookup"><span data-stu-id="23492-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<span data-ttu-id="23492-134">레지스트리 편집기를 사용하여 레지스트리에서 버전 정보를 찾거나 프로그래밍 방식으로 레지스트리를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-134">You can use Registry Editor to find version information in the registry, or you can query the registry programmatically.</span></span>

<a name="net_b"></a>

### <a name="use-registry-editor"></a><span data-ttu-id="23492-135">레지스트리 편집기 사용</span><span class="sxs-lookup"><span data-stu-id="23492-135">Use Registry Editor</span></span>

1. <span data-ttu-id="23492-136">**시작** 메뉴에서 **실행**을 선택하고 *regedit*을 입력한 다음, **OK**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-136">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="23492-137">regedit을 실행하려면 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-137">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="23492-138">레지스트리 편집기에서 다음 하위 키를 엽니다. **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="23492-138">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="23492-139">**전체**하위 키가 없으면 .NET Framework 4.5 이상이 설치되어 있지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23492-139">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23492-140">레지스트리의 **NET Framework Setup** 폴더는 마침표로 시작하지 ‘않습니다’.</span><span class="sxs-lookup"><span data-stu-id="23492-140">The **NET Framework Setup** folder in the registry does *not* begin with a period.</span></span>

3. <span data-ttu-id="23492-141">**릴리스**라는 DWORD 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-141">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="23492-142">릴리스 DWORD가 있으면 컴퓨터에 .NET Framework 4.5 이상이 설치된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23492-142">If it exists, then you have .NET Framework 4.5 or later installed.</span></span> <span data-ttu-id="23492-143">그 값은 특정 버전의 .NET Framework에 대응되는 릴리스 키입니다.</span><span class="sxs-lookup"><span data-stu-id="23492-143">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="23492-144">예를 들어, 다음 그림에서 **릴리스** 항목은 378389로, 이것은 .NET Framework 4.5.의 릴리스 키입니다.</span><span class="sxs-lookup"><span data-stu-id="23492-144">In the following figure, for example, the value of the **Release** entry is 378389, which is the release key for .NET Framework 4.5.</span></span>

   <span data-ttu-id="23492-145">![.NET Framework 4.5.에 대한 레지스트리 항목](./media/clr-installdir.png ".NET Framework 4.5.에 대한 레지스트리 항목")</span><span class="sxs-lookup"><span data-stu-id="23492-145">![Registry entry for the .NET Framework 4.5](./media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="23492-146">다음 표에는 .NET Framework 4.5 이상 버전의 각 운영 체제상의 **릴리스** DWORD가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-146">The following table lists the value of the **Release** DWORD on individual operating systems for .NET Framework 4.5 and later versions.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="23492-147">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="23492-147">.NET Framework version</span></span>|<span data-ttu-id="23492-148">릴리스 DWORD의 값</span><span class="sxs-lookup"><span data-stu-id="23492-148">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="23492-149">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="23492-149">.NET Framework 4.5</span></span>|<span data-ttu-id="23492-150">모든 Windows 운영 체제: 378389</span><span class="sxs-lookup"><span data-stu-id="23492-150">All Windows operating systems: 378389</span></span>|
|<span data-ttu-id="23492-151">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="23492-151">.NET Framework 4.5.1</span></span>|<span data-ttu-id="23492-152">Windows 8.1 및 Windows Server 2012 R2: 378675</span><span class="sxs-lookup"><span data-stu-id="23492-152">On Windows 8.1 and Windows Server 2012 R2: 378675</span></span><br /><span data-ttu-id="23492-153">다른 모든 Windows 운영 체제: 378758</span><span class="sxs-lookup"><span data-stu-id="23492-153">On all other Windows operating systems: 378758</span></span>|
|<span data-ttu-id="23492-154">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="23492-154">.NET Framework 4.5.2</span></span>|<span data-ttu-id="23492-155">모든 Windows 운영 체제: 379893</span><span class="sxs-lookup"><span data-stu-id="23492-155">All Windows operating systems: 379893</span></span>|
|<span data-ttu-id="23492-156">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="23492-156">.NET Framework 4.6</span></span>|<span data-ttu-id="23492-157">Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="23492-157">On Windows 10: 393295</span></span><br /><span data-ttu-id="23492-158">다른 모든 Windows 운영 체제: 393297</span><span class="sxs-lookup"><span data-stu-id="23492-158">On all other Windows operating systems: 393297</span></span>|
|<span data-ttu-id="23492-159">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="23492-159">.NET Framework 4.6.1</span></span>|<span data-ttu-id="23492-160">Windows 10 11월 업데이트 운영 체제: 394254</span><span class="sxs-lookup"><span data-stu-id="23492-160">On Windows 10 November Update systems: 394254</span></span><br /><span data-ttu-id="23492-161">다른 모든 Windows 운영 체제(Windows 10 포함): 394271</span><span class="sxs-lookup"><span data-stu-id="23492-161">On all other Windows operating systems (including Windows 10): 394271</span></span>|
|<span data-ttu-id="23492-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="23492-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="23492-163">Windows 10 1주년 업데이트 및 Windows Server 2016: 394802</span><span class="sxs-lookup"><span data-stu-id="23492-163">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><span data-ttu-id="23492-164">다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 394806</span><span class="sxs-lookup"><span data-stu-id="23492-164">On all other Windows operating systems (including other Windows 10 operating systems): 394806</span></span>|
|<span data-ttu-id="23492-165">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="23492-165">.NET Framework 4.7</span></span>|<span data-ttu-id="23492-166">Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="23492-166">On Windows 10 Creators Update: 460798</span></span><br /><span data-ttu-id="23492-167">다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 460805</span><span class="sxs-lookup"><span data-stu-id="23492-167">On all other Windows operating systems (including other Windows 10 operating systems): 460805</span></span>|
|<span data-ttu-id="23492-168">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="23492-168">.NET Framework 4.7.1</span></span>|<span data-ttu-id="23492-169">Windows 10 Fall Creators Update 및 Windows Server, 버전 1709: 461308</span><span class="sxs-lookup"><span data-stu-id="23492-169">On Windows 10 Fall Creators Update and Windows Server, version 1709: 461308</span></span><br/><span data-ttu-id="23492-170">다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 461310</span><span class="sxs-lookup"><span data-stu-id="23492-170">On all other Windows operating systems (including other Windows 10 operating systems): 461310</span></span>|
|<span data-ttu-id="23492-171">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="23492-171">.NET Framework 4.7.2</span></span>|<span data-ttu-id="23492-172">Windows 10 2018년 4월 업데이트 및 Windows Server, 버전 1803: 461808</span><span class="sxs-lookup"><span data-stu-id="23492-172">On Windows 10 April 2018 Update and Windows Server, version 1803: 461808</span></span><br/><span data-ttu-id="23492-173">Windows 10 2018년 4월 업데이트 및 Windows Server, 버전 1803 이외의 모든 Windows 운영 체제: 461814</span><span class="sxs-lookup"><span data-stu-id="23492-173">On all Windows operating systems other than Windows 10 April 2018 Update and Windows Server, version 1803: 461814</span></span>|
|<span data-ttu-id="23492-174">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="23492-174">.NET Framework 4.8</span></span>|<span data-ttu-id="23492-175">Windows 10 2019년 5월 업데이트 및 Windows 10 2019년 11월 업데이트: 528040</span><span class="sxs-lookup"><span data-stu-id="23492-175">On Windows 10 May 2019 Update and Windows 10 November 2019 Update: 528040</span></span><br/><span data-ttu-id="23492-176">다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 528049</span><span class="sxs-lookup"><span data-stu-id="23492-176">On all other Windows operating systems (including other Windows 10 operating systems): 528049</span></span>|

#### <a name="specific-version"></a><span data-ttu-id="23492-177">특정 버전</span><span class="sxs-lookup"><span data-stu-id="23492-177">Specific version</span></span>

<span data-ttu-id="23492-178">특정 버전의 .NET Framework가 *특정* 버전의 Windows 운영 체제에 설치되어 있는지 여부를 확인하려면 **릴리스** DWORD 값이 표에 나열된 값과 *동일한지* 테스트하세요.</span><span class="sxs-lookup"><span data-stu-id="23492-178">To determine whether a *specific* version of the .NET Framework is installed on a particular version of the Windows operating system, test whether the **Release** DWORD value is *equal to* the value listed in the table.</span></span> <span data-ttu-id="23492-179">예를 들어 .NET Framework 4.6이 Windows 10 시스템에 있는지 확인하려면 **릴리스** 값이 393295와 ‘같은지’ 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-179">For example, to determine whether .NET Framework 4.6 is present on a Windows 10 system, test for the a **Release** value that is *equal to* 393295.</span></span>

#### <a name="minimum-version"></a><span data-ttu-id="23492-180">최소 버전</span><span class="sxs-lookup"><span data-stu-id="23492-180">Minimum version</span></span>

<span data-ttu-id="23492-181">*최하* 버전의 .NET Framework가 있는지 확인하려면 이전 표에서 해당 버전에 대해 가장 작은 **릴리스** DWORD 값을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="23492-181">To determine whether a *minimum* version of the .NET Framework is present, use the smallest **RELEASE** DWORD value for that version from the previous table.</span></span> <span data-ttu-id="23492-182">(편의를 위해 다음 표에도 최솟값이 나열됩니다.)</span><span class="sxs-lookup"><span data-stu-id="23492-182">(For convenience, the minimum values are also listed in the table that follows.)</span></span>

<span data-ttu-id="23492-183">예를 들어 애플리케이션이 .NET Framework 4.8 이상 버전에서 실행되는 경우 528040과 *같거나 이보다 큰* **릴리스** DWORD 값을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-183">For example, if your application runs under .NET Framework 4.8 or a later version, test for a **RELEASE** DWORD value that is *greater than or equal to* 528040.</span></span>

|<span data-ttu-id="23492-184">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="23492-184">.NET Framework version</span></span>|<span data-ttu-id="23492-185">릴리스 DWORD의 최소 값</span><span class="sxs-lookup"><span data-stu-id="23492-185">Minimum value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="23492-186">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="23492-186">.NET Framework 4.5</span></span>|<span data-ttu-id="23492-187">378389</span><span class="sxs-lookup"><span data-stu-id="23492-187">378389</span></span>|
|<span data-ttu-id="23492-188">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="23492-188">.NET Framework 4.5.1</span></span>|<span data-ttu-id="23492-189">378675</span><span class="sxs-lookup"><span data-stu-id="23492-189">378675</span></span>|
|<span data-ttu-id="23492-190">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="23492-190">.NET Framework 4.5.2</span></span>|<span data-ttu-id="23492-191">379893</span><span class="sxs-lookup"><span data-stu-id="23492-191">379893</span></span>|
|<span data-ttu-id="23492-192">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="23492-192">.NET Framework 4.6</span></span>|<span data-ttu-id="23492-193">393295</span><span class="sxs-lookup"><span data-stu-id="23492-193">393295</span></span>|
|<span data-ttu-id="23492-194">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="23492-194">.NET Framework 4.6.1</span></span>|<span data-ttu-id="23492-195">394254</span><span class="sxs-lookup"><span data-stu-id="23492-195">394254</span></span>|
|<span data-ttu-id="23492-196">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="23492-196">.NET Framework 4.6.2</span></span>|<span data-ttu-id="23492-197">394802</span><span class="sxs-lookup"><span data-stu-id="23492-197">394802</span></span>|
|<span data-ttu-id="23492-198">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="23492-198">.NET Framework 4.7</span></span>|<span data-ttu-id="23492-199">460798</span><span class="sxs-lookup"><span data-stu-id="23492-199">460798</span></span>|
|<span data-ttu-id="23492-200">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="23492-200">.NET Framework 4.7.1</span></span>|<span data-ttu-id="23492-201">461308</span><span class="sxs-lookup"><span data-stu-id="23492-201">461308</span></span>|
|<span data-ttu-id="23492-202">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="23492-202">.NET Framework 4.7.2</span></span>|<span data-ttu-id="23492-203">461808</span><span class="sxs-lookup"><span data-stu-id="23492-203">461808</span></span>|
|<span data-ttu-id="23492-204">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="23492-204">.NET Framework 4.8</span></span>|<span data-ttu-id="23492-205">528040</span><span class="sxs-lookup"><span data-stu-id="23492-205">528040</span></span>|

#### <a name="multiple-versions"></a><span data-ttu-id="23492-206">여러 가지 버전</span><span class="sxs-lookup"><span data-stu-id="23492-206">Multiple versions</span></span>

<span data-ttu-id="23492-207">여러 버전을 테스트하려면 최신 .NET Framework 버전의 더 작은 DWORD 값과 ‘같거나 이보다 큰’ 값을 테스트한 후 연속적인 각 이전 버전에 대해 더 작은 DWORD 값과 비교하세요.</span><span class="sxs-lookup"><span data-stu-id="23492-207">To test for multiple versions, begin by testing for a value that is *greater than or equal to* the smaller DWORD value for the latest .NET Framework version, and then compare the value with the smaller DWORD value for each successive earlier version.</span></span> <span data-ttu-id="23492-208">예를 들어 애플리케이션에 .NET Framework 4.7 이상이 필요하고 특정 버전의 .NET Framework를 확인하려는 경우 461808(또는 .NET Framework 4.7.2의 경우는 더 작은 DWORD 값)과 ‘같거나 이보다 큰’ **릴리스** DWORD 값을 테스트하여 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-208">For example, if your application requires .NET Framework 4.7 or later and you want to determine the specific version of .NET Framework present, start by testing for a **RELEASE** DWORD value that is *great than or equal to* to 461808 (the smaller DWORD value for .NET Framework 4.7.2).</span></span> <span data-ttu-id="23492-209">그런 다음, 이 **릴리스** DWORD 값을 이후의 각 .NET Framework 버전에 대한 더 작은 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-209">Then compare the **RELEASE** DWORD value with the smaller value for each later .NET Framework version.</span></span>

<a name="net_d"></a>

### <a name="query-the-registry-using-code"></a><span data-ttu-id="23492-210">코드를 사용하여 레지스트리를 쿼리</span><span class="sxs-lookup"><span data-stu-id="23492-210">Query the registry using code</span></span>

1. <span data-ttu-id="23492-211"><xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType>와 <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType>메서드를 사용하여 Windows 레지스트리의**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** 하위 키에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-211">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

   <span data-ttu-id="23492-212">**릴리스** DWORD 항목이**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** 하위 키에 있으면 .NET Framework 4.5 이상 버전이 컴퓨터에 설치된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23492-212">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span>

2. <span data-ttu-id="23492-213">**릴리스** 항목값을 확인하여 설치된 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-213">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="23492-214">이후 버전과의 호환성을 유지하려는 경우 버전의 값이 [.NET Framework 버전 표](#version_table)에 나와 있는 값 이상인지를 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23492-214">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="23492-215">다음 예제에서는 레지스트리에서 **릴리스** 항목값을 확인하여 .NET Framework 4.5 이상 버전이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-215">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="23492-216">이 예제에서는 버전을 확인하기 위한 권장된 방법을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-216">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="23492-217">**릴리스**항목의 값이 알려진 릴리스 키의 값보다 *크거나 같은지* 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-217">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="23492-218">최신 버전에서 가장 오래된 버전 순서대로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-218">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a>

### <a name="use-powershell-to-check-for-a-minimum-required-version"></a><span data-ttu-id="23492-219">PowerShell을 사용하여 최소 필수 버전 확인</span><span class="sxs-lookup"><span data-stu-id="23492-219">Use PowerShell to check for a minimum-required version</span></span>

<span data-ttu-id="23492-220">PowerShell 명령을 사용하여 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** 하위 키의 **릴리스** 항목값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-220">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="23492-221">다음 예제에서는 **릴리스** 항목 값을 확인하여 .NET Framework 4.6.2 이상이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-221">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="23492-222">설치된 경우 `True` 코드 반환, 설치되지 않은 경우 `False` 코드 반환.</span><span class="sxs-lookup"><span data-stu-id="23492-222">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="23492-223">다른 최소 필수 .NET Framework 버전을 확인하려면 예제의 `394802`를 [.NET Framework 버전 표](#version_table)의 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="23492-223">To check for a different minimum-required .NET Framework version, replace `394802` in the example with a value from the [.NET Framework version table](#version_table).</span></span> <span data-ttu-id="23492-224">해당 버전에 대해 표시되는 가장 작은 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-224">Use the smallest value shown for that version.</span></span>

## <a name="find-older-net-framework-versions-1-through-4"></a><span data-ttu-id="23492-225">이전 .NET Framework 버전 찾기(1~4)</span><span class="sxs-lookup"><span data-stu-id="23492-225">Find older .NET Framework versions (1 through 4)</span></span>

<a name="net_a"></a>

### <a name="use-registry-editor-older-framework-versions"></a><span data-ttu-id="23492-226">레지스트리 편집기 사용(이전 프레임워크 버전)</span><span class="sxs-lookup"><span data-stu-id="23492-226">Use Registry Editor (older framework versions)</span></span>

1. <span data-ttu-id="23492-227">**시작** 메뉴에서 **실행**을 선택하고 *regedit*을 입력한 다음, **OK**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-227">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

    <span data-ttu-id="23492-228">regedit을 실행하려면 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-228">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="23492-229">레지스트리 편집기에서 다음 하위 키를 엽니다. **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span><span class="sxs-lookup"><span data-stu-id="23492-229">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>

    - <span data-ttu-id="23492-230">.NET Framework 버전 1.1~3.5의 경우, 각각 설치된 버전이 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** 하위 키 아래에 하위 키로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="23492-230">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="23492-231">예,**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="23492-231">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="23492-232">버전 번호는 버전 하위 키의 **Version** 항목에 값으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="23492-232">The version number is stored as a value in the version subkey's **Version** entry.</span></span>

    - <span data-ttu-id="23492-233">.NET Framework 4의 경우 **Version** 항목은 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** 하위 키 또는 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** 하위 키 아래에, 또는 두 하위 키 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-233">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23492-234">레지스트리의**NET Framework Setup**폴더는 마침표로 시작하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-234">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="23492-235">다음 그림은 .NET Framework 3.5의 하위 키와 **Version** 항목을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="23492-235">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="23492-236">![.NET Framework 3.5에 대한 레지스트리 항목](./media/net-4-and-earlier.png ".NET Framework 3.5 및 이전 버전")</span><span class="sxs-lookup"><span data-stu-id="23492-236">![The registry entry for the .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a>

### <a name="query-the-registry-using-code-older-framework-versions"></a><span data-ttu-id="23492-237">코드를 사용한 레지스트리 쿼리(이전 프레임워크 버전)</span><span class="sxs-lookup"><span data-stu-id="23492-237">Query the registry using code (older framework versions)</span></span>

<span data-ttu-id="23492-238"><xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>클래스를 사용하여 Windows 레지스트리의**HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** 하위 키에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-238">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="23492-239">다음 예제에서는 설치된 .NET Framework 1~4 버전을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-239">The following example finds the .NET Framework 1 through 4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a><span data-ttu-id="23492-240">CLR 버전 찾기</span><span class="sxs-lookup"><span data-stu-id="23492-240">Find CLR versions</span></span>

<a name="clr_a"></a>

### <a name="use-clrverexe"></a><span data-ttu-id="23492-241">Clrver.exe 사용</span><span class="sxs-lookup"><span data-stu-id="23492-241">Use Clrver.exe</span></span>

<span data-ttu-id="23492-242">[CLR 버전 도구(Clrver.exe)](../tools/clrver-exe-clr-version-tool.md)를 사용하여 컴퓨터에 설치된 공용 언어 런타임의 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-242">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="23492-243">[Visual Studio용 개발자 명령 프롬프트](../tools/developer-command-prompt-for-vs.md)에서 `clrver` 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-243">From a [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), enter `clrver`.</span></span>

    <span data-ttu-id="23492-244">샘플 출력:</span><span class="sxs-lookup"><span data-stu-id="23492-244">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="use-the-environment-class"></a><span data-ttu-id="23492-245">Environment 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="23492-245">Use the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23492-246">.NET Framework 4.5 이상의 경우 <xref:System.Environment.Version%2A?displayProperty=nameWithType>속성을 사용하여 런타임의 버전을 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-246">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="23492-247">대신 코드로 [.NET Framework 버전 4.5 이상 찾기](#net_d)에 설명된 것처럼 레지스트리를 쿼리하십시오.</span><span class="sxs-lookup"><span data-stu-id="23492-247">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="23492-248"><xref:System.Version>개체를 검색하기 위해 <xref:System.Environment.Version?displayProperty=nameWithType>속성을 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-248">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span>

    <span data-ttu-id="23492-249">반환된 `System.Version`개체는 현재 코드를 실행하는 런타임 버전을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-249">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="23492-250">컴퓨터에 설치된 어셈블리 버전이나 다른 런타임 버전은 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-250">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="23492-251">.NET Framework 버전 4, 4.5, 4.5.1 및 4.5.2의 경우 반환된 <xref:System.Version>개체 문자열 표현은 4.0.30319.*xxxxx* 형식이며, *xxxxx*는 42000보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-251">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*, where *xxxxx* is less than 42000.</span></span> <span data-ttu-id="23492-252">.NET Framework 4.6 및 이후 버전의 경우 형식은 4.0.30319.42000입니다.</span><span class="sxs-lookup"><span data-stu-id="23492-252">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>

2. <span data-ttu-id="23492-253">`Version`개체를 가져온 후, 다음과 같이 개체를 쿼리하십시오.</span><span class="sxs-lookup"><span data-stu-id="23492-253">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="23492-254">주 릴리스 식별자(예:버전 4.0의 경우 *4*)는 <xref:System.Version.Major%2A?displayProperty=nameWithType>속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-254">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="23492-255">부 릴리스 식별자(예:버전 4.0의 경우 *0*)는 <xref:System.Version.Minor%2A?displayProperty=nameWithType>속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-255">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="23492-256">전체 버전 문자열(예를 들어*4.0.30319.18010*)에는 <xref:System.Version.ToString%2A?displayProperty=nameWithType>메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-256">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="23492-257">메서드는 코드를 실행 하는 런타임 버전을 반영하는 단일 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-257">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="23492-258">이는 컴퓨터에 설치된 어셈블리 버전이나 다른 런타임 버전은 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23492-258">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>

<span data-ttu-id="23492-259">다음 예제에서는 <xref:System.Environment.Version%2A?displayProperty=nameWithType>속성을 사용하여 CLR 버전 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="23492-259">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="23492-260">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23492-260">See also</span></span>

- [<span data-ttu-id="23492-261">방법: 설치된 .NET Framework 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="23492-261">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="23492-262">개발자용 .NET Framework 설치</span><span class="sxs-lookup"><span data-stu-id="23492-262">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="23492-263">.NET Framework 버전 및 종속성</span><span class="sxs-lookup"><span data-stu-id="23492-263">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
