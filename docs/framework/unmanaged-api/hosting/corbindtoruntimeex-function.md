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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84e4c70c973fb19be6800d2cbaf76ea137f58b28
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767957"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="5d41f-102">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="5d41f-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="5d41f-103">관리 되지 않는 호스트의 CLR (공용 언어 런타임)을 프로세스로 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="5d41f-104">합니다 [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) 하 고 `CorBindToRuntimeEx` 함수는 동일한 작업을 수행 하지만 `CorBindToRuntimeEx` 함수를 사용 하면 CLR의 동작을 지정 하는 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-104">The [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="5d41f-105">.NET Framework 4에서이 함수에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="5d41f-106">이 함수는 다음을 수행 하는 데 사용 하는 매개 변수 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="5d41f-107">로드할 런타임 버전을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-107">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="5d41f-108">서버 또는 워크스테이션 빌드를 로드할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="5d41f-109">동시 가비지 수집 또는 비 동시 가비지 컬렉션을 수행할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d41f-110">동시 가비지 수집 WOW64를 실행 하는 응용 프로그램에서 지원 되지 않습니다 x86 에뮬레이터 (이전의 IA-64) Intel Itanium 아키텍처를 구현 하는 64 비트 시스템에서.</span><span class="sxs-lookup"><span data-stu-id="5d41f-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="5d41f-111">64 비트 Windows 시스템에서 WOW64를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [실행 중인 32 비트 응용 프로그램](/windows/desktop/WinProg64/running-32-bit-applications)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="5d41f-112">어셈블리가 도메인 중립적으로 로드 되는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="5d41f-113">에 대 한 인터페이스 포인터를 가져올는 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) CLR 인스턴스를 시작 하기 전에 구성에 대 한 추가 옵션을 설정 하려면 사용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-113">Obtain an interface pointer to an [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d41f-114">구문</span><span class="sxs-lookup"><span data-stu-id="5d41f-114">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5d41f-115">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d41f-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="5d41f-116">[in] 로드 하려는 CLR의 버전을 설명 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="5d41f-117">.NET Framework의 버전 번호는 마침표로 구분 하 여 네 부분으로 이루어져: *major.minor.build.revision*합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="5d41f-118">로 전달 되는 문자열 `pwszVersion` v"문자가" 뒤에 버전 번호 (예: "나옵니다 v1.0.1529")의 처음 세 부분이로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="5d41f-119">일부 버전의 CLR은 CLR의 이전 버전과 호환성을 지정 하는 정책 문을 사용 하 여 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="5d41f-120">기본적으로 시작 shim 평가 `pwszVersion` 정책 명령문 및 로드에 대 한 최신 버전의 런타임와 호환 되는 요청 된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="5d41f-121">호스트 정책 평가 건너뛰고 지정 된 정확한 버전을 로드 하 여 shim을 강제로 실행할 수 있습니다 `pwszVersion` 값을 전달 하 여 `STARTUP_LOADER_SAFEMODE` 에 대 한는 `startupFlags` 아래 설명 된 대로 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="5d41f-122">호출자가 null을 지정 하는 경우 `pwszVersion`, `CorBindToRuntimeEx` 설치 된 런타임 버전 번호가 있는.NET Framework 4 런타임 보다 작으면 및 해당 집합에서 최신 버전의 런타임 로드 집합을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="5d41f-123">이전 버전이 설치 된 경우.NET Framework 4 이상 및 실패를 로드 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="5d41f-124">Note는 null이 전달 제공 호스트는 런타임 버전이 로드 된 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="5d41f-125">이 방법은 일부 시나리오에서 적합할 수 있습니다, 있지만 것이 좋습니다 호스트를 로드 하려면 특정 버전을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="5d41f-126">[in] Clr 서버 또는 워크스테이션을 로드할지 여부를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="5d41f-127">유효한 값은 `svr` 및 `wks`입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="5d41f-128">서버 빌드는 가비지 컬렉션에 대 한 다중 프로세서를 활용 하도록 최적화 되어 워크스테이션 빌드 최적화 되 고 단일 프로세서 컴퓨터에서 실행 하는 클라이언트 응용 프로그램.</span><span class="sxs-lookup"><span data-stu-id="5d41f-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="5d41f-129">경우 `pwszBuildFlavor` 로 설정 된 워크스테이션 빌드가 null 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="5d41f-130">단일 프로세서 컴퓨터에서 실행 하는 경우 워크스테이션 빌드가 항상 로드 됩니다, 경우에 `pwszBuildFlavor` 로 설정 된 `svr`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="5d41f-131">그러나 경우 `pwszBuildFlavor` 로 설정 되어 `svr` 동시 가비지 컬렉션이 지정 되 고 (에 대 한 설명을 참조 하세요.를 `startupFlags` 매개 변수), 서버 빌드가 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="5d41f-132">[in] 값의 조합 된 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-132">[in] A combination of values of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="5d41f-133">동시 가비지 컬렉션, 도메인 중립 코드 및 동작을 제어 하는 이러한 플래그는 `pwszVersion` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="5d41f-134">기본값은 단일 도메인 플래그가 설정 된 경우.</span><span class="sxs-lookup"><span data-stu-id="5d41f-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="5d41f-135">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-135">The following values are valid:</span></span>  
  
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
  
 <span data-ttu-id="5d41f-136">이러한 플래그의 설명에 대 한 참조를 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-136">For descriptions of these flags, see the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="5d41f-137">[in] 합니다 `CLSID` 중 하나를 구현 하는 coclass의 합니다 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="5d41f-138">지원 되는 값은 CLSID_CorRuntimeHost CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="5d41f-139">[in] 합니다 `IID` 에서 요청된 된 인터페이스의 `rclsid`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="5d41f-140">지원 되는 값은 IID_ICorRuntimeHost IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="5d41f-141">[out] 반환 된 인터페이스 포인터를 `riid`입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d41f-142">설명</span><span class="sxs-lookup"><span data-stu-id="5d41f-142">Remarks</span></span>  
 <span data-ttu-id="5d41f-143">하는 경우 `pwszVersion` 존재 하지 않는 런타임 버전 지정 `CorBindToRuntimeEx` CLR_E_SHIM_RUNTIMELOAD의 HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="5d41f-144">실행 컨텍스트 및 Windows Id의 흐름</span><span class="sxs-lookup"><span data-stu-id="5d41f-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="5d41f-145">CLR의 버전 1 <xref:System.Security.Principal.WindowsIdentity> 개체 새 스레드를 스레드 풀 타이머 콜백을 등 비동기 지점 간을 흐르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="5d41f-146">Clr 버전 2.0에에서는 <xref:System.Threading.ExecutionContext> 개체는 현재 실행 중인 스레드에 대 한 일부 정보를 래핑하고 모든 비동기 지점에서 하지만 응용 프로그램 도메인 경계에 걸쳐 있지 흐름입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="5d41f-147">마찬가지로,는 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점 간에 개체도 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="5d41f-148">따라서 스레드에서 현재 가장 있으면도 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="5d41f-149">두 가지 방법으로 흐름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-149">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="5d41f-150">수정 하 여는 <xref:System.Threading.ExecutionContext> 스레드별 기준 흐름을 억제할 수 설정 (참조를 <xref:System.Threading.ExecutionContext.SuppressFlow%2A>를 <xref:System.Security.SecurityContext.SuppressFlow%2A>, 및 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> 메서드).</span><span class="sxs-lookup"><span data-stu-id="5d41f-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="5d41f-151">버전 1 호환성 모드로 프로세스 기본 모드를 변경 하 여 위치를 <xref:System.Security.Principal.WindowsIdentity> 개체에 관계 없이 모든 비동기 지점 간에 전달 되지 않습니다는 <xref:System.Threading.ExecutionContext> 현재 스레드에 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="5d41f-152">기본 모드를 변경 하는 방법을 CLR을 로드 하는 관리 되는 실행 파일 또는 관리 되지 않는 호스팅 인터페이스 사용 되는 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="5d41f-153">관리 되는 실행 파일을 설정 해야 합니다는 `enabled` 특성을 [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) 요소를 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="5d41f-154">관리 되지 않는 호스팅 인터페이스를 설정 합니다 `STARTUP_LEGACY_IMPERSONATION` 플래그를 `startupFlags` 호출 될 때 매개 변수는 `CorBindToRuntimeEx` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="5d41f-155">버전 1 호환성 모드에는 전체 프로세스 및 프로세스에서 모든 응용 프로그램 도메인에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d41f-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d41f-156">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d41f-156">Requirements</span></span>  
 <span data-ttu-id="5d41f-157">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d41f-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d41f-158">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d41f-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d41f-159">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d41f-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d41f-160">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d41f-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d41f-161">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d41f-161">See also</span></span>

- [<span data-ttu-id="5d41f-162">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="5d41f-162">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="5d41f-163">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="5d41f-163">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="5d41f-164">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="5d41f-164">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="5d41f-165">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="5d41f-165">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="5d41f-166">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d41f-166">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="5d41f-167">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="5d41f-167">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
