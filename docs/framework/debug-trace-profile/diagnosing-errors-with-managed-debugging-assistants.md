---
title: 관리 디버깅 도우미를 사용하여 오류 진단
description: 관리 디버깅 도우미를 사용 하 여 .NET에서 오류를 진단 합니다. Mda는 런타임 상태 정보를 제공 하기 위해 CLR과 함께 작동 하는 디버깅을 지원 합니다.
ms.date: 08/14/2018
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
ms.openlocfilehash: ac6fdc09fb057cc55659ce076d37ab96fe2354d1
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416098"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a><span data-ttu-id="edf9f-104">관리 디버깅 도우미를 사용 하 여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="edf9f-104">Diagnose Errors with Managed Debugging Assistants</span></span>

<span data-ttu-id="edf9f-105">MDA(관리 디버깅 도우미)는 런타임 상태에 대한 정보를 제공하기 위해 CLR(공용 언어 런타임)과 함께 작동하는 디버깅 도우미입니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-105">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="edf9f-106">이 도우미는 다른 방법으로는 트래핑할 수 없는 런타임 이벤트에 대한 정보 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-106">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="edf9f-107">MDA를 사용하면 관리 코드와 비관리 코드 간에 변환할 때 발생하는 찾기 어려운 애플리케이션 버그를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-107">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span>

<span data-ttu-id="edf9f-108">Windows 레지스트리에 키를 추가 하거나 환경 변수를 설정 하 여 모든 Mda를 [사용 하거나 사용 하지 않도록](#enable-and-disable-mdas) 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-108">You can [enable or disable](#enable-and-disable-mdas) all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="edf9f-109">애플리케이션 구성 설정을 사용하여 특정 MDA를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-109">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="edf9f-110">애플리케이션의 구성 파일에서 일부 개별 MDA에 대한 추가 구성 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-110">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="edf9f-111">이러한 구성 파일은 런타임이 로드될 때 구문 분석되므로 관리되는 애플리케이션이 시작되기 전에 MDA를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-111">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="edf9f-112">이미 시작된 애플리케이션에 대해서는 MDA를 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-112">You cannot enable it for applications that have already started.</span></span>

<span data-ttu-id="edf9f-113">다음 표에서는 .NET Framework와 함께 제공 되는 Mda를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-113">The following table lists the MDAs that ship with the .NET Framework:</span></span>

|||
|-|-|
|[<span data-ttu-id="edf9f-114">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="edf9f-114">asynchronousThreadAbort</span></span>](asynchronousthreadabort-mda.md)|[<span data-ttu-id="edf9f-115">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="edf9f-115">bindingFailure</span></span>](bindingfailure-mda.md)|
|[<span data-ttu-id="edf9f-116">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="edf9f-116">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="edf9f-117">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="edf9f-117">contextSwitchDeadlock</span></span>](contextswitchdeadlock-mda.md)|
|[<span data-ttu-id="edf9f-118">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="edf9f-118">dangerousThreadingAPI</span></span>](dangerousthreadingapi-mda.md)|[<span data-ttu-id="edf9f-119">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="edf9f-119">dateTimeInvalidLocalFormat</span></span>](datetimeinvalidlocalformat-mda.md)|
|[<span data-ttu-id="edf9f-120">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="edf9f-120">dirtyCastAndCallOnInterface</span></span>](dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="edf9f-121">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="edf9f-121">disconnectedContext</span></span>](disconnectedcontext-mda.md)|
|[<span data-ttu-id="edf9f-122">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="edf9f-122">dllMainReturnsFalse</span></span>](dllmainreturnsfalse-mda.md)|[<span data-ttu-id="edf9f-123">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="edf9f-123">exceptionSwallowedOnCallFromCom</span></span>](exceptionswallowedoncallfromcom-mda.md)|
|[<span data-ttu-id="edf9f-124">failedQI</span><span class="sxs-lookup"><span data-stu-id="edf9f-124">failedQI</span></span>](failedqi-mda.md)|[<span data-ttu-id="edf9f-125">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="edf9f-125">fatalExecutionEngineError</span></span>](fatalexecutionengineerror-mda.md)|
|[<span data-ttu-id="edf9f-126">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="edf9f-126">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="edf9f-127">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="edf9f-127">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)|
|[<span data-ttu-id="edf9f-128">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="edf9f-128">illegalPrepareConstrainedRegion</span></span>](illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="edf9f-129">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="edf9f-129">invalidApartmentStateChange</span></span>](invalidapartmentstatechange-mda.md)|
|[<span data-ttu-id="edf9f-130">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="edf9f-130">invalidCERCall</span></span>](invalidcercall-mda.md)|[<span data-ttu-id="edf9f-131">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="edf9f-131">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)|
|[<span data-ttu-id="edf9f-132">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="edf9f-132">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)|[<span data-ttu-id="edf9f-133">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="edf9f-133">invalidIUnknown</span></span>](invalidiunknown-mda.md)|
|[<span data-ttu-id="edf9f-134">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="edf9f-134">invalidMemberDeclaration</span></span>](invalidmemberdeclaration-mda.md)|[<span data-ttu-id="edf9f-135">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="edf9f-135">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)|
|[<span data-ttu-id="edf9f-136">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="edf9f-136">invalidVariant</span></span>](invalidvariant-mda.md)|[<span data-ttu-id="edf9f-137">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="edf9f-137">jitCompilationStart</span></span>](jitcompilationstart-mda.md)|
|[<span data-ttu-id="edf9f-138">loaderLock</span><span class="sxs-lookup"><span data-stu-id="edf9f-138">loaderLock</span></span>](loaderlock-mda.md)|[<span data-ttu-id="edf9f-139">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="edf9f-139">loadFromContext</span></span>](loadfromcontext-mda.md)|
|[<span data-ttu-id="edf9f-140">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="edf9f-140">marshalCleanupError</span></span>](marshalcleanuperror-mda.md)|[<span data-ttu-id="edf9f-141">marshaling</span><span class="sxs-lookup"><span data-stu-id="edf9f-141">marshaling</span></span>](marshaling-mda.md)|
|[<span data-ttu-id="edf9f-142">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="edf9f-142">memberInfoCacheCreation</span></span>](memberinfocachecreation-mda.md)|[<span data-ttu-id="edf9f-143">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="edf9f-143">moduloObjectHashcode</span></span>](moduloobjecthashcode-mda.md)|
|[<span data-ttu-id="edf9f-144">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="edf9f-144">nonComVisibleBaseClass</span></span>](noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="edf9f-145">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="edf9f-145">notMarshalable</span></span>](notmarshalable-mda.md)|
|[<span data-ttu-id="edf9f-146">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="edf9f-146">openGenericCERCall</span></span>](opengenericcercall-mda.md)|[<span data-ttu-id="edf9f-147">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="edf9f-147">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)|
|[<span data-ttu-id="edf9f-148">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="edf9f-148">pInvokeLog</span></span>](pinvokelog-mda.md)|[<span data-ttu-id="edf9f-149">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="edf9f-149">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)|
|[<span data-ttu-id="edf9f-150">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="edf9f-150">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)|[<span data-ttu-id="edf9f-151">가능성</span><span class="sxs-lookup"><span data-stu-id="edf9f-151">reentrancy</span></span>](reentrancy-mda.md)|
|[<span data-ttu-id="edf9f-152">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="edf9f-152">releaseHandleFailed</span></span>](releasehandlefailed-mda.md)|[<span data-ttu-id="edf9f-153">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="edf9f-153">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)|
|[<span data-ttu-id="edf9f-154">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="edf9f-154">streamWriterBufferedDataLost</span></span>](streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="edf9f-155">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="edf9f-155">virtualCERCall</span></span>](virtualcercall-mda.md)|

<span data-ttu-id="edf9f-156">기본적으로 .NET Framework는 모든 관리되는 디버거에 대한 MDA의 하위 집합을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-156">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="edf9f-157">**Windows**  >  **디버그** 메뉴에서 Windows**예외 설정** 을 선택 하 고 **관리 디버깅 도우미** 목록을 확장 하 여 Visual Studio의 기본 집합을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-157">You can view the default set in Visual Studio by choosing **Windows** > **Exception Settings** on the **Debug** menu, and then expanding the **Managed Debugging Assistants** list.</span></span>

![Visual Studio의 예외 설정 창](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a><span data-ttu-id="edf9f-159">Mda 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="edf9f-159">Enable and Disable MDAs</span></span>

<span data-ttu-id="edf9f-160">레지스트리 키, 환경 변수 및 애플리케이션 구성 설정을 사용하여 MDA를 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-160">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="edf9f-161">애플리케이션 구성 설정을 사용하려면 레지스트리 키 또는 환경 변수를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-161">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>

> [!TIP]
> <span data-ttu-id="edf9f-162">Mda를 사용 하지 않도록 설정 하는 대신 MDA 알림이 수신 될 때마다 Visual Studio에서 MDA 대화 상자를 표시 하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-162">Instead of disabling MDAs, you can prevent Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="edf9f-163">이렇게 하려면 **Windows**  >  **디버그** 메뉴에서 Windows**예외 설정** 을 선택 하 고 **관리 디버깅 도우미** 목록을 확장 한 다음 개별 MDA에 대 한 **throw 될 때 중단** 확인란을 선택 하거나 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-163">To do that, choose **Windows** > **Exception Settings** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Break When Thrown** check box for the individual MDA.</span></span>

### <a name="registry-key"></a><span data-ttu-id="edf9f-164">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="edf9f-164">Registry Key</span></span>

<span data-ttu-id="edf9f-165">Mda를 사용 하도록 설정 하려면 \*\*HKEY_LOCAL_MACHINE \software\microsoft를 추가 \\ 합니다. \*\*Windows 레지스트리에 있는 NETFramework\MDA 하위 키 (유형 REG_SZ, 값 1)입니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-165">To enable MDAs, add the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA** subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="edf9f-166">다음 예제를 *Mdaenable .reg*라는 텍스트 파일에 복사 합니다. Windows 레지스트리 편집기 (RegEdit.exe)를 열고 **파일** 메뉴에서 **가져오기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-166">Copy the following example into a text file named *MDAEnable.reg*. Open the Windows Registry Editor (RegEdit.exe), and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="edf9f-167">*Mdaenable .reg* 파일을 선택 하 여 해당 컴퓨터에서 mda를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-167">Select the *MDAEnable.reg* file to enable MDAs on that computer.</span></span> <span data-ttu-id="edf9f-168">하위 키를 문자열 값 **1** (DWORD 값 **1**이 아님)로 설정 하면 *ApplicationName*.mda.config 파일에서 MDA 설정을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-168">Setting the subkey to string value of **1** (not DWORD value of **1**) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="edf9f-169">예를 들어 메모장의 MDA 구성 파일 이름은 notepad.exe.mda.config입니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-169">For example, the MDA configuration file for Notepad would be named notepad.exe.mda.config.</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="edf9f-170">컴퓨터가 64비트 운영 체제에서 32비트 애플리케이션을 실행 중인 경우 MDA 키는 다음과 같이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-170">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="edf9f-171">자세한 내용은 [응용 프로그램별 구성 설정](#application-specific-configuration-settings) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="edf9f-171">See [Application-Specific Configuration Settings](#application-specific-configuration-settings) for more information.</span></span> <span data-ttu-id="edf9f-172">레지스트리 설정은 COMPLUS_MDA 환경 변수로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-172">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="edf9f-173">자세한 내용은 [환경 변수](#environment-variable) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="edf9f-173">See [Environment Variable](#environment-variable) for more information.</span></span>

<span data-ttu-id="edf9f-174">Mda를 사용 하지 않도록 설정 하려면 Windows 레지스트리 편집기를 사용 하 여 MDA 하위 키를 **0** (영)으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-174">To disable MDAs, set the MDA subkey to **0** (zero) using the Windows Registry Editor.</span></span>

<span data-ttu-id="edf9f-175">기본적으로 일부 MDA는 디버거에 연결된 애플리케이션을 실행하면 레지스트리 키를 추가하지 않더라도 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-175">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="edf9f-176">이 섹션의 앞부분에서 설명한 대로 *Mdadisable .reg* 파일을 실행 하 여 이러한 도우미를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-176">You can disable these assistants by running the *MDADisable.reg* file as described earlier in this section.</span></span>

### <a name="environment-variable"></a><span data-ttu-id="edf9f-177">환경 변수</span><span class="sxs-lookup"><span data-stu-id="edf9f-177">Environment Variable</span></span>

<span data-ttu-id="edf9f-178">MDA 활성화는 레지스트리 키를 재정의하는 환경 변수 COMPLUS_MDA에 의해서도 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-178">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="edf9f-179">COMPLUS_MDA 문자열은 대/소문자를 구분하지 않으며, 세미콜론으로 구분된 MDA 이름 또는 기타 특수 제어 문자열의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-179">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="edf9f-180">관리되는 디버거 또는 관리되지 않는 디버거에서 시작하면 기본적으로 MDA 집합이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-180">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="edf9f-181">이러한 설정은 디버거에서 기본적으로 사용하도록 설정된, 세미콜론으로 구분된 MDA 목록을 환경 변수 또는 레지스트리 키 값에 추가하여 암시적으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-181">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="edf9f-182">특수 제어 문자열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-182">The special control strings are the following:</span></span>

- <span data-ttu-id="edf9f-183">`0` - 모든 MDA를 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-183">`0` - Deactivates all MDAs.</span></span>

- <span data-ttu-id="edf9f-184">`1` - *ApplicationName*.mda.config에서 MDA 설정을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-184">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>

- <span data-ttu-id="edf9f-185">`managedDebugger` - 관리되는 실행 파일이 디버거에서 시작되면 암시적으로 활성화되는 모든 MDA를 명시적으로 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-185">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>

- <span data-ttu-id="edf9f-186">`unmanagedDebugger` - 관리되지 않는 실행 파일이 디버거에서 시작되면 암시적으로 활성화되는 모든 MDA를 명시적으로 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-186">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>

<span data-ttu-id="edf9f-187">충돌하는 설정이 있는 경우 최신 설정이 이전 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-187">If there are conflicting settings, the most recent settings override previous settings:</span></span>

- <span data-ttu-id="edf9f-188">`COMPLUS_MDA=0`은 디버거에서 암시적으로 사용하도록 설정된 MDA를 포함하여 모든 MDA를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-188">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="edf9f-189">`COMPLUS_MDA=gcUnmanagedToManaged`는 디버거에서 암시적으로 사용하도록 설정된 모든 MDA 외에 `gcUnmanagedToManaged`를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-189">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="edf9f-190">`COMPLUS_MDA=0;gcUnmanagedToManaged`는 `gcUnmanagedToManaged`를 사용하도록 설정하지만 디버거에서 달리 암시적으로 사용하도록 설정되지 않는 MDA를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-190">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>

### <a name="application-specific-configuration-settings"></a><span data-ttu-id="edf9f-191">응용 프로그램별 구성 설정</span><span class="sxs-lookup"><span data-stu-id="edf9f-191">Application-Specific Configuration Settings</span></span>

<span data-ttu-id="edf9f-192">애플리케이션의 MDA 구성 파일에서 일부 도우미를 개별적으로 사용하도록 설정, 사용하지 않도록 설정 및 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-192">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="edf9f-193">MDA를 구성하는 데 애플리케이션 구성 파일을 사용할 수 있으려면 MDA 레지스트리 키 또는 COMPLUS_MDA 환경 변수를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-193">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="edf9f-194">애플리케이션 구성 파일은 일반적으로 애플리케이션 실행 파일(.exe)과 동일한 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-194">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="edf9f-195">파일 이름은 *ApplicationName*.mda.config 형식으로 사용 합니다. 예를 들어 notepad.exe.mda.config 합니다. 응용 프로그램 구성 파일에서 사용 하도록 설정 된 도우미에는 해당 도우미의 동작을 제어 하기 위해 특별히 디자인 된 특성 또는 요소가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-195">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span>

<span data-ttu-id="edf9f-196">다음 예제에서는 [마샬링을](marshaling-mda.md)사용 하도록 설정 하 고 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-196">The following example shows how to enable and configure the [marshaling](marshaling-mda.md):</span></span>

```xml
<mdaConfig>
  <assistants>
    <marshaling>
      <methodFilter>
        <match name="*"/>
      </methodFilter>
      <fieldFilter>
        <match name="*"/>
      </fieldFilter>
    </marshaling>
  </assistants>
</mdaConfig>
```

<span data-ttu-id="edf9f-197">`Marshaling` MDA는 애플리케이션에서 각 관리되는-관리되지 않는 변환의 관리되지 않는 형식으로 마샬링되는 관리되는 형식에 대한 정보를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-197">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="edf9f-198">`Marshaling`MDA는 각각 **methodfilter** 및 **fieldfilter** 자식 요소에 제공 된 메서드 및 구조 필드의 이름을 필터링 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-198">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the **methodFilter** and **fieldFilter** child elements, respectively.</span></span>

<span data-ttu-id="edf9f-199">다음 예제에서는 기본 설정을 사용 하 여 여러 Mda를 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-199">The following example shows how to enable multiple MDAs by using their default settings:</span></span>

```xml
<mdaConfig>
  <assistants>
    <illegalPrepareConstrainedRegion />
    <invalidCERCall />
    <openGenericCERCall />
    <virtualCERCall />
  </assistants>
</mdaConfig>
```

> [!IMPORTANT]
> <span data-ttu-id="edf9f-200">구성 파일에 둘 이상의 도우미를 지정할 때는 사전순으로 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-200">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="edf9f-201">예를 들어, `virtualCERCall` MDA와 `invalidCERCall` MDA를 둘 다 사용하도록 설정하려면 `<invalidCERCall />` 항목 앞에 `<virtualCERCall />` 항목을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-201">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="edf9f-202">항목이 사전순이 아니면 처리되지 않은 잘못된 구성 파일 예외 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-202">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>

## <a name="mda-exceptions"></a><span data-ttu-id="edf9f-203">MDA 예외</span><span class="sxs-lookup"><span data-stu-id="edf9f-203">MDA exceptions</span></span>

<span data-ttu-id="edf9f-204">MDA가 활성화 되 면 코드가 디버거에서 실행 되지 않는 경우에도 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-204">When an MDA is enabled, it's active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="edf9f-205">디버거가 없을 때 MDA 이벤트가 발생하면 이벤트 메시지가 처리되지 않은 예외가 아니더라도 처리되지 않은 예외 대화 상자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-205">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="edf9f-206">이 대화 상자가 표시되지 않도록 하려면 코드가 디버깅 환경에서 실행되지 않는 경우 MDA 사용 설정을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="edf9f-206">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>

<span data-ttu-id="edf9f-207">Visual Studio IDE (통합 개발 환경)에서 코드가 실행 되는 경우 특정 MDA 이벤트에 대해 표시 되는 예외 대화 상자를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-207">When your code executes in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="edf9f-208">이렇게 하려면 **디버그** 메뉴에서 **Windows**  >  **예외 설정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-208">To do that, on the **Debug** menu, choose **Windows** > **Exception Settings**.</span></span> <span data-ttu-id="edf9f-209">**예외 설정** 창에서 **관리 디버깅 도우미** 목록을 확장 한 다음 개별 MDA에 대 한 **throw 될 때 중단** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-209">In the **Exception Settings** window, expand the **Managed Debugging Assistants** list, and then clear the **Break When Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="edf9f-210">이 대화 상자를 사용 하 여 MDA 예외 대화 *상자를 표시할* 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf9f-210">You can also use this dialog box to *enable* the display of MDA exception dialog boxes.</span></span>

## <a name="mda-output"></a><span data-ttu-id="edf9f-211">MDA 출력</span><span class="sxs-lookup"><span data-stu-id="edf9f-211">MDA Output</span></span>

<span data-ttu-id="edf9f-212">MDA 출력은 mda의 출력을 보여 주는 다음 예제와 유사 합니다 `PInvokeStackImbalance` .</span><span class="sxs-lookup"><span data-stu-id="edf9f-212">MDA output is similar to the following example, which shows the output from the `PInvokeStackImbalance` MDA:</span></span>

<span data-ttu-id="edf9f-213">**PInvoke 함수 ' MDATest!를 호출 합니다. MDATest. Program:: StdCall '이 (가) 스택에서 불균형 했습니다. 이는 관리 되는 PInvoke 서명이 관리 되지 않는 대상 시그니처와 일치 하지 않기 때문일 수 있습니다. PInvoke 시그니처의 호출 규칙 및 매개 변수가 관리 되지 않는 대상 시그니처와 일치 하는지 확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="edf9f-213">**A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="see-also"></a><span data-ttu-id="edf9f-214">추가 정보</span><span class="sxs-lookup"><span data-stu-id="edf9f-214">See also</span></span>

- [<span data-ttu-id="edf9f-215">디버깅, 추적 및 프로파일링</span><span class="sxs-lookup"><span data-stu-id="edf9f-215">Debugging, Tracing, and Profiling</span></span>](index.md)
