---
title: ICLRMetaHost::GetRuntime 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9889ddf1c03f14835101f31d0a3b264f0016267
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676553"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="32988-102">ICLRMetaHost::GetRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="32988-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="32988-103">가져옵니다 합니다 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 는 CLR (공용 언어 런타임)의 특정 버전에 해당 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="32988-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="32988-104">이 메서드를 대체 합니다 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수를 사용 합니다 [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="32988-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32988-105">구문</span><span class="sxs-lookup"><span data-stu-id="32988-105">Syntax</span></span>  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32988-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32988-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="32988-107">[in] .NET Framework 컴파일 버전 메타 데이터 형식으로 저장 "v*A*. *B*[. *X*] "입니다.</span><span class="sxs-lookup"><span data-stu-id="32988-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="32988-108">*A*, *B*, 및 *X* 는 주 버전, 부 버전 및 빌드 번호에 해당 하는 10 진수입니다.</span><span class="sxs-lookup"><span data-stu-id="32988-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32988-109">이 매개 변수는 C:\Windows\Microsoft.NET\Framework 또는 C:\Windows\Microsoft.NET\Framework64 아래 표시 된 대로.NET Framework 버전의 경우 디렉터리 이름이 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32988-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="32988-110">예제 값은 "v1.0.3705", "v1.1.4322", "v2.0.50727" 및 "v4.0"입니다. *X*", 여기서 *X* 설치 빌드 번호에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="32988-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="32988-111">"V" 접두사는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="32988-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="32988-112">[in] 원하는 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="32988-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="32988-113">현재이 매개 변수에 대 한 유일한 유효 값은 IID_ICLRRuntimeInfo 합니다.</span><span class="sxs-lookup"><span data-stu-id="32988-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="32988-114">[out] 에 대 한 포인터를 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 요청된 된 런타임을에 해당 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="32988-114">[out] A pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32988-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="32988-115">Return Value</span></span>  
 <span data-ttu-id="32988-116">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="32988-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="32988-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32988-117">HRESULT</span></span>|<span data-ttu-id="32988-118">설명</span><span class="sxs-lookup"><span data-stu-id="32988-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32988-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="32988-119">S_OK</span></span>|<span data-ttu-id="32988-120">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="32988-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="32988-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="32988-121">E_POINTER</span></span>|<span data-ttu-id="32988-122">`pwzVersion` 또는 `ppRuntime`이 null입니다.</span><span class="sxs-lookup"><span data-stu-id="32988-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32988-123">설명</span><span class="sxs-lookup"><span data-stu-id="32988-123">Remarks</span></span>  
 <span data-ttu-id="32988-124">이 메서드가 상호 작용 하는 일관 되 게 레거시 인터페이스를 사용 하 여 같은 합니다 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 사용 되지 않는 등의 인터페이스 및 레거시 기능 `CorBindTo*` 함수 (참조 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) 호스팅 API는.NET Framework 2.0에서).</span><span class="sxs-lookup"><span data-stu-id="32988-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="32988-125">즉, 기존 API를 사용 하 여 로드 된 런타임을 새 API에 표시 되며 새 API를 사용 하 여 로드 된 런타임을 레거시 API에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32988-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32988-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32988-126">Requirements</span></span>  
 <span data-ttu-id="32988-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="32988-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32988-128">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="32988-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="32988-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="32988-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32988-130">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32988-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32988-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="32988-131">See also</span></span>
- [<span data-ttu-id="32988-132">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32988-132">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="32988-133">사용되지 않는 CLR 호스팅 인터페이스 및 Coclass</span><span class="sxs-lookup"><span data-stu-id="32988-133">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="32988-134">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32988-134">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="32988-135">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="32988-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="32988-136">호스팅</span><span class="sxs-lookup"><span data-stu-id="32988-136">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
