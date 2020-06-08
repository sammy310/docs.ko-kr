---
title: CorBindToRuntimeEx 함수
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeEx
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeEx
helpviewer_keywords:
- CorBindToRuntimeEx function [.NET Framework hosting]
ms.assetid: aae9fb17-5d01-41da-9773-1b5b5b642d81
topic_type:
- apiref
ms.openlocfilehash: e66b63ffa4ed25e861cff6bd9eb6065f57ff807f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493502"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="68f6a-102">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="68f6a-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="68f6a-103">관리 되지 않는 호스트에서 CLR (공용 언어 런타임)을 프로세스로 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="68f6a-104">[CorBindToRuntime](corbindtoruntime-function.md) 및 `CorBindToRuntimeEx` 함수는 동일한 작업을 수행 하지만 함수를 `CorBindToRuntimeEx` 사용 하 여 CLR의 동작을 지정 하는 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-104">The [CorBindToRuntime](corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="68f6a-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="68f6a-106">이 함수는 호스트에서 다음 작업을 수행할 수 있도록 하는 매개 변수 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="68f6a-107">로드할 런타임 버전을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-107">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="68f6a-108">서버 또는 워크스테이션 빌드를 로드할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="68f6a-109">동시 가비지 수집 또는 비 동시 가비지 수집 수행 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68f6a-110">Intel Itanium 아키텍처 (이전의 IA-64)를 구현 하는 64 비트 시스템에서 WOW64 x86 에뮬레이터를 실행 하는 응용 프로그램에서는 동시 가비지 수집이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="68f6a-111">64 비트 Windows 시스템에서 WOW64를 사용 하는 방법에 대 한 자세한 내용은 [32 비트 응용 프로그램 실행](/windows/desktop/WinProg64/running-32-bit-applications)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f6a-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="68f6a-112">어셈블리가 도메인 중립적으로 로드 되는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="68f6a-113">CLR 인스턴스를 시작 하기 전에 구성 하기 위한 추가 옵션을 설정 하는 데 사용할 수 있는 [ICorRuntimeHost](icorruntimehost-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-113">Obtain an interface pointer to an [ICorRuntimeHost](icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68f6a-114">구문</span><span class="sxs-lookup"><span data-stu-id="68f6a-114">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,
    [in]  LPCWSTR      pwszBuildFlavor,
    [in]  DWORD        startupFlags,
    [in]  REFCLSID     rclsid,
    [in]  REFIID       riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68f6a-115">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68f6a-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="68f6a-116">진행 로드 하려는 CLR의 버전을 설명 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="68f6a-117">.NET Framework의 버전 번호는 마침표로 구분 된 네 부분으로 구성 되어 있습니다. 주 버전. 부 버전. *빌드. 수정 버전*.</span><span class="sxs-lookup"><span data-stu-id="68f6a-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="68f6a-118">로 전달 된 문자열은 `pwszVersion` "v" 문자 뒤에 버전 번호의 처음 세 부분 (예: "v 1.0.1529")을 사용 하 여 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="68f6a-119">CLR의 이전 버전과의 호환성을 지정 하는 정책 문과 함께 일부 CLR 버전이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="68f6a-120">기본적으로 시작 shim은 `pwszVersion` 정책 문에 대해 평가 하 고 요청 되는 버전과 호환 되는 최신 버전의 런타임을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="68f6a-121">호스트는 `pwszVersion` `STARTUP_LOADER_SAFEMODE` 아래에 `startupFlags` 설명 된 대로 매개 변수에 대 한 값을 전달 하 여 shim이 정책 평가를 건너뛰고에 지정 된 정확한 버전을 로드 하도록 강제 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="68f6a-122">호출자가에 대해 null을 지정 하는 경우는 `pwszVersion` `CorBindToRuntimeEx` 버전 번호가 .NET Framework 4 런타임 보다 낮은 설치 된 런타임 집합을 식별 하 고 해당 집합에서 최신 버전의 런타임을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="68f6a-123">.NET Framework 4 이상을 로드 하지 않으며, 이전 버전이 설치 되어 있지 않으면 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="68f6a-124">Null을 전달 하면 로드 되는 런타임 버전을 호스트에서 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="68f6a-125">이 방법은 일부 시나리오에서 적합할 수 있지만 호스트에서 로드할 특정 버전을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="68f6a-126">진행 CLR의 워크스테이션 빌드 또는 서버를 로드할지 여부를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="68f6a-127">유효한 값은 `svr` 및 `wks`입니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="68f6a-128">서버 빌드는 가비지 컬렉션에 대해 여러 프로세서를 활용 하도록 최적화 되며 워크스테이션 빌드는 단일 프로세서 컴퓨터에서 실행 되는 클라이언트 응용 프로그램에 최적화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="68f6a-129">`pwszBuildFlavor`가 null로 설정 된 경우 워크스테이션 빌드가 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="68f6a-130">단일 프로세서 컴퓨터에서 실행 되 `pwszBuildFlavor` 는 경우가로 설정 된 경우에도 워크스테이션 빌드가 항상 로드 됩니다 `svr` .</span><span class="sxs-lookup"><span data-stu-id="68f6a-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="68f6a-131">그러나 `pwszBuildFlavor` 가로 설정 되 `svr` 고 동시 가비지 수집이 지정 된 경우 (매개 변수에 대 한 설명 참조 `startupFlags` ) 서버 빌드가 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="68f6a-132">진행 [STARTUP_FLAGS](startup-flags-enumeration.md) 열거형 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-132">[in] A combination of values of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="68f6a-133">이러한 플래그는 동시 가비지 컬렉션, 도메인 중립 코드 및 매개 변수의 동작을 제어 `pwszVersion` 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="68f6a-134">플래그가 설정 되지 않은 경우 기본값은 단일 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="68f6a-135">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-135">The following values are valid:</span></span>  
  
- `STARTUP_CONCURRENT_GC`  
  
- `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
- `STARTUP_LOADER_SAFEMODE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_LOADER_SETPREFERENCE`  
  
- `STARTUP_SERVER_GC`  
  
- `STARTUP_HOARD_GC_VM`  
  
- `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
- `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 <span data-ttu-id="68f6a-136">이러한 플래그에 대 한 설명은 [STARTUP_FLAGS](startup-flags-enumeration.md) 열거를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f6a-136">For descriptions of these flags, see the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="68f6a-137">진행 [ICorRuntimeHost](icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="68f6a-138">지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="68f6a-139">진행 `IID`에서 요청 된 인터페이스의입니다 `rclsid` .</span><span class="sxs-lookup"><span data-stu-id="68f6a-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="68f6a-140">지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="68f6a-141">제한이 에 대해 반환 된 인터페이스 포인터 `riid` 입니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68f6a-142">설명</span><span class="sxs-lookup"><span data-stu-id="68f6a-142">Remarks</span></span>  
 <span data-ttu-id="68f6a-143">`pwszVersion`가 존재 하지 않는 런타임 버전을 지정 하는 경우 `CorBindToRuntimeEx` CLR_E_SHIM_RUNTIMELOAD HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="68f6a-144">Windows Id의 실행 컨텍스트 및 흐름</span><span class="sxs-lookup"><span data-stu-id="68f6a-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="68f6a-145">CLR 버전 1에서 <xref:System.Security.Principal.WindowsIdentity> 개체는 새 스레드, 스레드 풀 또는 타이머 콜백과 같은 비동기 요소를 통해 전달 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="68f6a-146">CLR 버전 2.0에서 <xref:System.Threading.ExecutionContext> 개체는 현재 실행 중인 스레드에 대 한 일부 정보를 래핑하고 응용 프로그램 도메인 경계를 넘어 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="68f6a-147">마찬가지로, <xref:System.Security.Principal.WindowsIdentity> 개체도 모든 비동기 지점에서 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="68f6a-148">따라서 스레드의 현재 가장 (있는 경우)는 흐름이 너무 많습니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="68f6a-149">흐름은 다음 두 가지 방법으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-149">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="68f6a-150"><xref:System.Threading.ExecutionContext>스레드 단위로 흐름을 표시 하지 않도록 설정 수정 ( <xref:System.Threading.ExecutionContext.SuppressFlow%2A> , <xref:System.Security.SecurityContext.SuppressFlow%2A> 및 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> 메서드 참조)</span><span class="sxs-lookup"><span data-stu-id="68f6a-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="68f6a-151">프로세스 기본 모드를 버전 1 호환성 모드로 변경 하 여 <xref:System.Security.Principal.WindowsIdentity> 현재 스레드의 설정에 관계 없이 개체가 비동기 지점에서 이동 하지 않습니다 <xref:System.Threading.ExecutionContext> .</span><span class="sxs-lookup"><span data-stu-id="68f6a-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="68f6a-152">기본 모드를 변경 하는 방법은 관리 되는 실행 파일 또는 관리 되지 않는 호스팅 인터페이스를 사용 하 여 CLR을 로드 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="68f6a-153">관리 되는 실행 파일의 경우 요소의 특성을로 설정 해야 합니다 `enabled` [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) `true` .</span><span class="sxs-lookup"><span data-stu-id="68f6a-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="68f6a-154">관리 되지 않는 호스팅 인터페이스의 경우 `STARTUP_LEGACY_IMPERSONATION` `startupFlags` 함수를 호출할 때 매개 변수에서 플래그를 설정 합니다 `CorBindToRuntimeEx` .</span><span class="sxs-lookup"><span data-stu-id="68f6a-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="68f6a-155">버전 1 호환성 모드는 전체 프로세스와 프로세스의 모든 응용 프로그램 도메인에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68f6a-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68f6a-156">요구 사항</span><span class="sxs-lookup"><span data-stu-id="68f6a-156">Requirements</span></span>  
 <span data-ttu-id="68f6a-157">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68f6a-157">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68f6a-158">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="68f6a-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68f6a-159">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="68f6a-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68f6a-160">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68f6a-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f6a-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68f6a-161">See also</span></span>

- [<span data-ttu-id="68f6a-162">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="68f6a-162">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="68f6a-163">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="68f6a-163">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="68f6a-164">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="68f6a-164">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="68f6a-165">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="68f6a-165">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="68f6a-166">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68f6a-166">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="68f6a-167">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="68f6a-167">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
