---
title: CorBindToRuntime 함수
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
ms.openlocfilehash: 2db9d26ef2dec150977c468b16334a7cb4b3d49c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176515"
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="97aec-102">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="97aec-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="97aec-103">관리되지 않는 호스트가 공통 언어 런타임(CLR)을 프로세스에 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="97aec-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97aec-105">구문</span><span class="sxs-lookup"><span data-stu-id="97aec-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,
    [in]  LPCWSTR     pwszBuildFlavor,
    [in]  REFCLSID    rclsid,
    [in]  REFIID      riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97aec-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97aec-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="97aec-107">【인】 로드할 CLR 버전을 설명하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="97aec-108">.NET Framework의 버전 번호는 마침표로 구분되는 네 부분으로 *구성됩니다.*</span><span class="sxs-lookup"><span data-stu-id="97aec-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="97aec-109">문자열은 문자 `pwszVersion` "v"로 시작하고 버전 번호의 처음 세 부분(예: "v1.0.1529")으로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="97aec-110">일부 CLR 버전은 이전 CLR 버전과의 호환성을 지정하는 정책 설명과 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="97aec-111">기본적으로 시작 심은 `pwszVersion` 정책 문에 대해 평가하고 요청되는 버전과 호환되는 런타임의 최신 버전을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="97aec-112">호스트는 shim을 강제로 정책 평가를 건너뛰고 아래에 `pwszVersion` 설명된 대로 `STARTUP_LOADER_SAFEMODE` `flags` 매개 변수에 대한 값을 전달하여 지정된 정확한 버전을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="97aec-113">호출자에게 null을 `pwszVersion`지정하는 경우 최신 버전의 런타임이 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="97aec-114">null을 전달하면 호스트가 로드되는 런타임 버전을 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="97aec-115">이 방법은 일부 시나리오에서 적절할 수 있지만 호스트가 로드할 특정 버전을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="97aec-116">【인】 서버를 로드할지 또는 CLR의 워크스테이션 빌드를 로드할지 여부를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="97aec-117">유효한 값은 `svr` 및 `wks`입니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="97aec-118">서버 빌드는 가비지 수집을 위해 여러 프로세서를 활용하도록 최적화되었으며 워크스테이션 빌드는 단일 프로세서 컴퓨터에서 실행되는 클라이언트 응용 프로그램에 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="97aec-119">null로 설정된 경우 `pwszBuildFlavor` 워크스테이션 빌드가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="97aec-120">단일 프로세서 컴퓨터에서 실행할 때 워크스테이션 빌드는 로 설정되어 `pwszBuildFlavor` 있더라도 `svr`항상 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="97aec-121">그러나 `pwszBuildFlavor` `svr` 설정되어 있고 동시 가비지 수집이 `flags` 지정되면(매개 변수 설명 참조) 서버 빌드가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="97aec-122">진행 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="97aec-123">지원되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="97aec-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="97aec-124">【인】 에서 `IID` `rclsid`요청된 인터페이스의</span><span class="sxs-lookup"><span data-stu-id="97aec-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="97aec-125">지원되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="97aec-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="97aec-126">【아웃】 반환된 인터페이스 `riid`포인터에 대해 .</span><span class="sxs-lookup"><span data-stu-id="97aec-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97aec-127">설명</span><span class="sxs-lookup"><span data-stu-id="97aec-127">Remarks</span></span>  
 <span data-ttu-id="97aec-128">존재하지 `pwszVersion` 않는 런타임 버전을 지정하면 CLR_E_SHIM_RUNTIMELOAD `CorBindToRuntimeEx` HRESULT 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="97aec-129">Windows ID의 실행 컨텍스트 및 흐름</span><span class="sxs-lookup"><span data-stu-id="97aec-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="97aec-130">CLR의 버전 1에서 <xref:System.Security.Principal.WindowsIdentity> 개체는 새 스레드, 스레드 풀 또는 타이머 콜백과 같은 비동기 지점에서 흐르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="97aec-131">CLR의 버전 2.0에서 <xref:System.Threading.ExecutionContext> 개체는 현재 실행 중인 스레드에 대한 일부 정보를 래핑하고 응용 프로그램 도메인 경계를 넘지 않고 비동기 지점을 가로질러 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="97aec-132">마찬가지로 개체는 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점을 가로질러흐기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="97aec-133">따라서 스레드의 현재 가장(있는 경우)도 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="97aec-134">다음 두 가지 방법으로 흐름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-134">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="97aec-135"><xref:System.Threading.ExecutionContext> 스레드별로 흐름을 억제하도록 설정을 수정합니다(의 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> 이 및 메서드 참조). <xref:System.Threading.ExecutionContext.SuppressFlow%2A> <xref:System.Security.SecurityContext.SuppressFlow%2A></span><span class="sxs-lookup"><span data-stu-id="97aec-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="97aec-136">프로세스 기본 모드를 버전 1 호환성 모드로 <xref:System.Security.Principal.WindowsIdentity> 변경하여 현재 스레드의 <xref:System.Threading.ExecutionContext> 설정에 관계없이 개체가 비동기 지점을 가로질러 흐르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="97aec-137">기본 모드를 변경하는 방법은 관리되는 실행 관리 항목 또는 관리되지 않는 호스팅 인터페이스를 사용하여 CLR을 로드할지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="97aec-138">관리되는 실행 경우 `enabled` [ \<레거시 사칭정책>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) 요소의 특성을 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="97aec-139">관리되지 않는 호스팅 인터페이스의 `STARTUP_LEGACY_IMPERSONATION` 경우 `flags` 함수를 호출할 때 매개 변수에 플래그를 설정합니다. `CorBindToRuntimeEx`</span><span class="sxs-lookup"><span data-stu-id="97aec-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="97aec-140">버전 1 호환성 모드는 전체 프로세스및 프로세스의 모든 응용 프로그램 도메인에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97aec-141">설명</span><span class="sxs-lookup"><span data-stu-id="97aec-141">Remarks</span></span>  
 <span data-ttu-id="97aec-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) `CorBindToRuntime` 및 동일한 작업을 수행하지만 이 `CorBindToRuntimeEx` 기능을 사용하면 플래그를 설정하여 CLR의 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97aec-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97aec-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97aec-143">Requirements</span></span>  
 <span data-ttu-id="97aec-144">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97aec-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97aec-145">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="97aec-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97aec-146">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="97aec-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97aec-147">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97aec-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97aec-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97aec-148">See also</span></span>

- [<span data-ttu-id="97aec-149">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="97aec-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="97aec-150">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="97aec-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="97aec-151">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="97aec-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="97aec-152">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="97aec-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="97aec-153">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97aec-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="97aec-154">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="97aec-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
