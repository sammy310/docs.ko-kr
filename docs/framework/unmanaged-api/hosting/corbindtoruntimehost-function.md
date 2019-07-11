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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 630e0c20309b6e791991b64ef8d423ff927b70fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767907"
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="2f4c4-102">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="2f4c4-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="2f4c4-103">호스트를 프로세스에는 CLR (공용 언어 런타임)의 지정된 된 버전을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="2f4c4-104">.NET Framework 4에서이 함수에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f4c4-105">구문</span><span class="sxs-lookup"><span data-stu-id="2f4c4-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2f4c4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f4c4-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="2f4c4-107">[in] 로드 하려는 CLR의 버전을 설명 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="2f4c4-108">.NET Framework의 버전 번호는 마침표로 구분 하 여 네 부분으로 이루어져: *major.minor.build.revision*합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="2f4c4-109">로 전달 되는 문자열 `pwszVersion` v"문자가" 뒤에 버전 번호 (예: "나옵니다 v1.0.1529")의 처음 세 부분이로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="2f4c4-110">일부 버전의 CLR은 CLR의 이전 버전과 호환성을 지정 하는 정책 문을 사용 하 여 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="2f4c4-111">기본적으로 시작 shim 평가 `pwszVersion` 정책 명령문 및 로드에 대 한 최신 버전의 런타임와 호환 되는 요청 된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="2f4c4-112">호스트 정책 평가 건너뛰고 지정 된 정확한 버전을 로드 하 여 shim을 강제로 실행할 수 있습니다 `pwszVersion` STARTUP_LOADER_SAFEMODE에 대 한 값을 전달 하 여는 `startupFlags` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="2f4c4-113">하는 경우 `pwszVersion` 는 `null,` 메서드가 CLR의 버전을 로드 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="2f4c4-114">대신 CLR_E_SHIM_RUNTIMELOAD 런타임을 로드 하지 못했음을 나타내는 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="2f4c4-115">[in] Clr 서버 또는 워크스테이션을 로드할지 여부를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="2f4c4-116">유효한 값은 `svr` 및 `wks`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="2f4c4-117">서버 빌드는 가비지 컬렉션에 대 한 다중 프로세서를 활용 하도록 최적화 되어 워크스테이션 빌드 최적화 되 고 단일 프로세서 컴퓨터에서 실행 하는 클라이언트 응용 프로그램.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="2f4c4-118">경우 `pwszBuildFlavor` 로 설정 된 워크스테이션 빌드가 null 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="2f4c4-119">단일 프로세서 컴퓨터에서 실행 하는 경우 워크스테이션 빌드가 항상 로드 됩니다, 경우에 `pwszBuildFlavor` 로 설정 된 `svr`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="2f4c4-120">그러나 경우 `pwszBuildFlavor` 로 설정 되어 `svr` 동시 가비지 컬렉션이 지정 되 고 (에 대 한 설명을 참조 하세요.를 `startupFlags` 매개 변수), 서버 빌드가 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f4c4-121">동시 가비지 수집 WOW64를 실행 하는 응용 프로그램에서 지원 되지 않습니다 x86 에뮬레이터 (이전의 IA-64) Intel Itanium 아키텍처를 구현 하는 64 비트 시스템에서.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="2f4c4-122">64 비트 Windows 시스템에서 WOW64를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [실행 중인 32 비트 응용 프로그램](/windows/desktop/WinProg64/running-32-bit-applications)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="2f4c4-123">[in] 로드 하기 위해 CLR의 버전을 지정 하는 호스트 구성 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="2f4c4-124">파일 이름에 정규화 된 경로가 포함 되어 있지 않으면, 호출을 수행 하는 실행 파일과 동일한 디렉터리에 있는 파일을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="2f4c4-125">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="2f4c4-126">[in] 동시 가비지 컬렉션, 도메인 중립 코드 및 동작을 제어 하는 플래그 집합을 `pwszVersion` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="2f4c4-127">기본값은 단일 도메인 플래그가 설정 된 경우.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="2f4c4-128">지원 되는 값 목록에 대해서는 [STARTUP_FLAGS 열거형](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="2f4c4-129">[in] 합니다 `CLSID` 중 하나를 구현 하는 coclass의 합니다 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="2f4c4-130">지원 되는 값은 CLSID_CorRuntimeHost CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="2f4c4-131">[in] `IID` 요청 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="2f4c4-132">지원 되는 값은 IID_ICorRuntimeHost IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="2f4c4-133">[out] 로드 된 런타임 버전에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f4c4-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f4c4-134">Requirements</span></span>  
 <span data-ttu-id="2f4c4-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f4c4-136">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="2f4c4-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="2f4c4-137">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f4c4-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f4c4-138">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f4c4-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f4c4-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f4c4-139">See also</span></span>

- [<span data-ttu-id="2f4c4-140">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="2f4c4-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="2f4c4-141">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="2f4c4-141">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="2f4c4-142">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="2f4c4-142">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="2f4c4-143">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="2f4c4-143">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="2f4c4-144">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f4c4-144">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="2f4c4-145">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="2f4c4-145">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
