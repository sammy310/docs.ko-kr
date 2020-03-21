---
title: CorBindToRuntimeHost 함수
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeHost
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeHost
helpviewer_keywords:
- CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type:
- apiref
ms.openlocfilehash: 6566adc442034763e0209869404b60b5afa63866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176489"
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="7a464-102">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="7a464-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="7a464-103">호스트가 지정된 버전의 공통 언어 런타임(CLR)을 프로세스에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="7a464-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a464-105">구문</span><span class="sxs-lookup"><span data-stu-id="7a464-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,
    [in] LPCWSTR       pwszBuildFlavor,
    [in] LPCWSTR       pwszHostConfigFile,
    [in] VOID*         pReserved,
    [in] DWORD         startupFlags,
    [in] REFCLSID      rclsid,
    [in] REFIID        riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a464-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7a464-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="7a464-107">【인】 로드할 CLR 버전을 설명하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="7a464-108">.NET Framework의 버전 번호는 마침표로 구분되는 네 부분으로 *구성됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7a464-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="7a464-109">문자열은 문자 `pwszVersion` "v"로 시작하고 버전 번호의 처음 세 부분(예: "v1.0.1529")으로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="7a464-110">일부 CLR 버전은 이전 CLR 버전과의 호환성을 지정하는 정책 설명과 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="7a464-111">기본적으로 시작 심은 `pwszVersion` 정책 문에 대해 평가하고 요청되는 버전과 호환되는 런타임의 최신 버전을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="7a464-112">호스트는 shim을 강제로 정책 평가를 건너뛰고 매개 `pwszVersion` 변수에 대한 STARTUP_LOADER_SAFEMODE 값을 `startupFlags` 전달하여 지정된 정확한 버전을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="7a464-113">이 `pwszVersion` `null,` 경우 메서드는 CLR의 모든 버전을 로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="7a464-114">대신 런타임을 로드하지 못했음을 나타내는 CLR_E_SHIM_RUNTIMELOAD 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="7a464-115">【인】 서버를 로드할지 또는 CLR의 워크스테이션 빌드를 로드할지 여부를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="7a464-116">유효한 값은 `svr` 및 `wks`입니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="7a464-117">서버 빌드는 가비지 수집을 위해 여러 프로세서를 활용하도록 최적화되었으며 워크스테이션 빌드는 단일 프로세서 컴퓨터에서 실행되는 클라이언트 응용 프로그램에 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="7a464-118">null로 설정된 경우 `pwszBuildFlavor` 워크스테이션 빌드가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="7a464-119">단일 프로세서 컴퓨터에서 실행할 때 워크스테이션 빌드는 로 설정되어 `pwszBuildFlavor` 있더라도 `svr`항상 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="7a464-120">그러나 `pwszBuildFlavor` `svr` 설정되어 있고 동시 가비지 수집이 `startupFlags` 지정되면(매개 변수 설명 참조) 서버 빌드가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a464-121">인텔 이타늄 아키텍처(이전의 IA-64)를 구현하는 64비트 시스템에서 WOW64 x86 에뮬레이터를 실행하는 응용 프로그램에서는 동시 가비지 수집이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="7a464-122">64비트 Windows 시스템에서 WOW64를 사용하는 방법에 대한 자세한 내용은 [32비트 응용 프로그램 실행을](/windows/desktop/WinProg64/running-32-bit-applications)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a464-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="7a464-123">【인】 로드할 CLR 버전을 지정하는 호스트 구성 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="7a464-124">파일 이름에 정규화된 경로가 포함되지 않은 경우 파일은 호출하는 실행 파일과 동일한 디렉터리에 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="7a464-125">【인】 향후 확장성을 위해 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="7a464-126">【인】 동시 가비지 수집, 도메인 중립 코드 및 매개 변수의 `pwszVersion` 동작을 제어하는 플래그 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="7a464-127">플래그가 설정되지 않은 경우 기본값은 단일 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="7a464-128">지원되는 값 목록은 STARTUP_FLAGS [열거형](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a464-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="7a464-129">진행 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="7a464-130">지원되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="7a464-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="7a464-131">【인】 요청하는 `IID` 인터페이스의 입니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="7a464-132">지원되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="7a464-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="7a464-133">【아웃】 로드된 런타임 버전에 대한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7a464-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a464-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a464-134">Requirements</span></span>  
 <span data-ttu-id="7a464-135">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a464-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a464-136">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="7a464-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="7a464-137">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7a464-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a464-138">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a464-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a464-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a464-139">See also</span></span>

- [<span data-ttu-id="7a464-140">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="7a464-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="7a464-141">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="7a464-141">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="7a464-142">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="7a464-142">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="7a464-143">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="7a464-143">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="7a464-144">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a464-144">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="7a464-145">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="7a464-145">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
