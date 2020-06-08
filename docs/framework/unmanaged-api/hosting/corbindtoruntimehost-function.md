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
ms.openlocfilehash: 9d1c7f4f5b881f7f55539602c152b557a7950472
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504409"
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="d684f-102">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="d684f-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="d684f-103">호스트에서 지정 된 버전의 CLR (공용 언어 런타임)을 프로세스로 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="d684f-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d684f-105">구문</span><span class="sxs-lookup"><span data-stu-id="d684f-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d684f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d684f-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="d684f-107">진행 로드 하려는 CLR의 버전을 설명 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="d684f-108">.NET Framework의 버전 번호는 마침표로 구분 된 네 부분으로 구성 되어 있습니다. 주 버전. 부 버전. *빌드. 수정 버전*.</span><span class="sxs-lookup"><span data-stu-id="d684f-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="d684f-109">로 전달 된 문자열은 `pwszVersion` "v" 문자 뒤에 버전 번호의 처음 세 부분 (예: "v 1.0.1529")을 사용 하 여 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="d684f-110">CLR의 이전 버전과의 호환성을 지정 하는 정책 문과 함께 일부 CLR 버전이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="d684f-111">기본적으로 시작 shim은 `pwszVersion` 정책 문에 대해 평가 하 고 요청 되는 버전과 호환 되는 최신 버전의 런타임을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="d684f-112">호스트는 `pwszVersion` 매개 변수에 대 한 STARTUP_LOADER_SAFEMODE 값을 전달 하 여 shim이 정책 평가를 건너뛰고에 지정 된 정확한 버전을 로드 하도록 강제할 수 있습니다 `startupFlags` .</span><span class="sxs-lookup"><span data-stu-id="d684f-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="d684f-113">`pwszVersion`가 이면 `null,` 메서드는 CLR의 모든 버전을 로드 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="d684f-114">대신 CLR_E_SHIM_RUNTIMELOAD를 반환 하며,이는 런타임을 로드 하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="d684f-115">진행 CLR의 워크스테이션 빌드 또는 서버를 로드할지 여부를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="d684f-116">유효한 값은 `svr` 및 `wks`입니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="d684f-117">서버 빌드는 가비지 컬렉션에 대해 여러 프로세서를 활용 하도록 최적화 되며 워크스테이션 빌드는 단일 프로세서 컴퓨터에서 실행 되는 클라이언트 응용 프로그램에 최적화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="d684f-118">`pwszBuildFlavor`가 null로 설정 된 경우 워크스테이션 빌드가 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="d684f-119">단일 프로세서 컴퓨터에서 실행 되 `pwszBuildFlavor` 는 경우가로 설정 된 경우에도 워크스테이션 빌드가 항상 로드 됩니다 `svr` .</span><span class="sxs-lookup"><span data-stu-id="d684f-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="d684f-120">그러나 `pwszBuildFlavor` 가로 설정 되 `svr` 고 동시 가비지 수집이 지정 된 경우 (매개 변수에 대 한 설명 참조 `startupFlags` ) 서버 빌드가 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d684f-121">Intel Itanium 아키텍처 (이전의 IA-64)를 구현 하는 64 비트 시스템에서 WOW64 x86 에뮬레이터를 실행 하는 응용 프로그램에서는 동시 가비지 수집이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="d684f-122">64 비트 Windows 시스템에서 WOW64를 사용 하는 방법에 대 한 자세한 내용은 [32 비트 응용 프로그램 실행](/windows/desktop/WinProg64/running-32-bit-applications)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d684f-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="d684f-123">진행 로드할 CLR 버전을 지정 하는 호스트 구성 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="d684f-124">파일 이름에 정규화 된 경로가 포함 되어 있지 않으면 파일은 호출 하는 실행 파일과 동일한 디렉터리에 있는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="d684f-125">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="d684f-126">진행 동시 가비지 컬렉션, 도메인 중립 코드 및 매개 변수의 동작을 제어 하는 플래그 집합입니다 `pwszVersion` .</span><span class="sxs-lookup"><span data-stu-id="d684f-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="d684f-127">플래그가 설정 되지 않은 경우 기본값은 단일 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="d684f-128">지원 되는 값 목록은 [STARTUP_FLAGS 열거](startup-flags-enumeration.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d684f-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="d684f-129">진행 [ICorRuntimeHost](icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="d684f-130">지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="d684f-131">진행 `IID`요청 하는 인터페이스의입니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="d684f-132">지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="d684f-133">제한이 로드 된 런타임 버전에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d684f-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d684f-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d684f-134">Requirements</span></span>  
 <span data-ttu-id="d684f-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d684f-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d684f-136">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d684f-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d684f-137">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d684f-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d684f-138">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d684f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d684f-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d684f-139">See also</span></span>

- [<span data-ttu-id="d684f-140">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="d684f-140">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="d684f-141">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="d684f-141">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="d684f-142">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="d684f-142">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="d684f-143">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="d684f-143">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="d684f-144">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d684f-144">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="d684f-145">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="d684f-145">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
