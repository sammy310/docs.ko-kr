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
ms.openlocfilehash: 3520af5f55f43183920dce7fbd24b70359c023a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176502"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="bc78f-102">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="bc78f-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="bc78f-103">관리되지 않는 호스트가 공통 언어 런타임(CLR)을 프로세스에 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="bc78f-104">[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) 및 `CorBindToRuntimeEx` 함수는 동일한 작업을 수행하지만 이 함수를 `CorBindToRuntimeEx` 사용하면 플래그를 설정하여 CLR의 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-104">The [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="bc78f-105">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="bc78f-106">이 함수는 호스트가 다음을 수행할 수 있도록 하는 매개 변수 집합을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="bc78f-107">로드할 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-107">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="bc78f-108">서버 또는 워크스테이션 빌드를 로드할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="bc78f-109">동시 가비지 수집 또는 비동시 가비지 수집이 수행되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc78f-110">인텔 이타늄 아키텍처(이전의 IA-64)를 구현하는 64비트 시스템에서 WOW64 x86 에뮬레이터를 실행하는 응용 프로그램에서는 동시 가비지 수집이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="bc78f-111">64비트 Windows 시스템에서 WOW64를 사용하는 방법에 대한 자세한 내용은 [32비트 응용 프로그램 실행을](/windows/desktop/WinProg64/running-32-bit-applications)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc78f-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="bc78f-112">어셈블리가 도메인 중립으로 로드되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="bc78f-113">CLR이 시작되기 전에 CLR의 인스턴스를 구성하기 위한 추가 옵션을 설정하는 데 사용할 수 있는 [ICorRuntimeHost에](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 대한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-113">Obtain an interface pointer to an [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc78f-114">구문</span><span class="sxs-lookup"><span data-stu-id="bc78f-114">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bc78f-115">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc78f-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="bc78f-116">【인】 로드할 CLR 버전을 설명하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="bc78f-117">.NET Framework의 버전 번호는 마침표로 구분되는 네 부분으로 *구성됩니다.*</span><span class="sxs-lookup"><span data-stu-id="bc78f-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="bc78f-118">문자열은 문자 `pwszVersion` "v"로 시작하고 버전 번호의 처음 세 부분(예: "v1.0.1529")으로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="bc78f-119">일부 CLR 버전은 이전 CLR 버전과의 호환성을 지정하는 정책 설명과 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="bc78f-120">기본적으로 시작 심은 `pwszVersion` 정책 문에 대해 평가하고 요청되는 버전과 호환되는 런타임의 최신 버전을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="bc78f-121">호스트는 shim을 강제로 정책 평가를 건너뛰고 아래에 `pwszVersion` 설명된 대로 `STARTUP_LOADER_SAFEMODE` `startupFlags` 매개 변수에 대한 값을 전달하여 지정된 정확한 버전을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="bc78f-122">호출자가 null for를 `pwszVersion`지정하는 경우 .NET Framework 4 런타임보다 버전 번호가 낮은 설치된 런타임 집합을 `CorBindToRuntimeEx` 식별하고 해당 집합에서 최신 버전의 런타임을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="bc78f-123">.NET Framework 4 이상은 로드되지 않으며 이전 버전이 설치되지 않으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="bc78f-124">null을 전달하면 호스트가 로드되는 런타임 버전을 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="bc78f-125">이 방법은 일부 시나리오에서 적절할 수 있지만 호스트가 로드할 특정 버전을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="bc78f-126">【인】 서버를 로드할지 또는 CLR의 워크스테이션 빌드를 로드할지 여부를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="bc78f-127">유효한 값은 `svr` 및 `wks`입니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="bc78f-128">서버 빌드는 가비지 수집을 위해 여러 프로세서를 활용하도록 최적화되었으며 워크스테이션 빌드는 단일 프로세서 컴퓨터에서 실행되는 클라이언트 응용 프로그램에 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="bc78f-129">null로 설정된 경우 `pwszBuildFlavor` 워크스테이션 빌드가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="bc78f-130">단일 프로세서 컴퓨터에서 실행할 때 워크스테이션 빌드는 로 설정되어 `pwszBuildFlavor` 있더라도 `svr`항상 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="bc78f-131">그러나 `pwszBuildFlavor` `svr` 설정되어 있고 동시 가비지 수집이 `startupFlags` 지정되면(매개 변수 설명 참조) 서버 빌드가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="bc78f-132">【인】 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 열거형의 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-132">[in] A combination of values of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="bc78f-133">이러한 플래그는 동시 가비지 수집, 도메인 중립 `pwszVersion` 코드 및 매개 변수의 동작을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="bc78f-134">플래그가 설정되지 않은 경우 기본값은 단일 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="bc78f-135">유효한 값은</span><span class="sxs-lookup"><span data-stu-id="bc78f-135">The following values are valid:</span></span>  
  
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
  
 <span data-ttu-id="bc78f-136">이러한 플래그에 대한 설명은 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 열거를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc78f-136">For descriptions of these flags, see the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="bc78f-137">진행 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="bc78f-138">지원되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="bc78f-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="bc78f-139">【인】 에서 `IID` `rclsid`요청된 인터페이스의</span><span class="sxs-lookup"><span data-stu-id="bc78f-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="bc78f-140">지원되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="bc78f-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="bc78f-141">【아웃】 반환된 인터페이스 `riid`포인터에 대해 .</span><span class="sxs-lookup"><span data-stu-id="bc78f-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc78f-142">설명</span><span class="sxs-lookup"><span data-stu-id="bc78f-142">Remarks</span></span>  
 <span data-ttu-id="bc78f-143">존재하지 `pwszVersion` 않는 런타임 버전을 지정하면 CLR_E_SHIM_RUNTIMELOAD `CorBindToRuntimeEx` HRESULT 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="bc78f-144">Windows ID의 실행 컨텍스트 및 흐름</span><span class="sxs-lookup"><span data-stu-id="bc78f-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="bc78f-145">CLR의 버전 1에서 <xref:System.Security.Principal.WindowsIdentity> 개체는 새 스레드, 스레드 풀 또는 타이머 콜백과 같은 비동기 지점에서 흐르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="bc78f-146">CLR의 버전 2.0에서 <xref:System.Threading.ExecutionContext> 개체는 현재 실행 중인 스레드에 대한 일부 정보를 래핑하고 응용 프로그램 도메인 경계를 넘지 않고 비동기 지점을 가로질러 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="bc78f-147">마찬가지로 개체는 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점을 가로질러흐기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="bc78f-148">따라서 스레드의 현재 가장(있는 경우)도 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="bc78f-149">다음 두 가지 방법으로 흐름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-149">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="bc78f-150"><xref:System.Threading.ExecutionContext> 스레드별로 흐름을 억제하도록 설정을 수정합니다(의 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> 이 및 메서드 참조). <xref:System.Threading.ExecutionContext.SuppressFlow%2A> <xref:System.Security.SecurityContext.SuppressFlow%2A></span><span class="sxs-lookup"><span data-stu-id="bc78f-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="bc78f-151">프로세스 기본 모드를 버전 1 호환성 모드로 <xref:System.Security.Principal.WindowsIdentity> 변경하여 현재 스레드의 <xref:System.Threading.ExecutionContext> 설정에 관계없이 개체가 비동기 지점을 가로질러 흐르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="bc78f-152">기본 모드를 변경하는 방법은 관리되는 실행 관리 항목 또는 관리되지 않는 호스팅 인터페이스를 사용하여 CLR을 로드할지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="bc78f-153">관리되는 실행 경우 `enabled` [ \<레거시 사칭정책>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) 요소의 특성을 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="bc78f-154">관리되지 않는 호스팅 인터페이스의 `STARTUP_LEGACY_IMPERSONATION` 경우 `startupFlags` 함수를 호출할 때 매개 변수에 플래그를 설정합니다. `CorBindToRuntimeEx`</span><span class="sxs-lookup"><span data-stu-id="bc78f-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="bc78f-155">버전 1 호환성 모드는 전체 프로세스및 프로세스의 모든 응용 프로그램 도메인에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc78f-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc78f-156">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc78f-156">Requirements</span></span>  
 <span data-ttu-id="bc78f-157">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc78f-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc78f-158">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="bc78f-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc78f-159">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bc78f-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc78f-160">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc78f-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc78f-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc78f-161">See also</span></span>

- [<span data-ttu-id="bc78f-162">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="bc78f-162">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="bc78f-163">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="bc78f-163">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="bc78f-164">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="bc78f-164">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="bc78f-165">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="bc78f-165">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="bc78f-166">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc78f-166">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="bc78f-167">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="bc78f-167">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
