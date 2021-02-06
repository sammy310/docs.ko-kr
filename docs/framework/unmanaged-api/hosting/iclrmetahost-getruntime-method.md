---
description: '자세히 알아보기: ICLRMetaHost:: GetRuntime 메서드'
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
ms.openlocfilehash: 8a2ada652dbb139337150cb8ed20986ebf8ae7f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637523"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="2a2a3-103">ICLRMetaHost::GetRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="2a2a3-103">ICLRMetaHost::GetRuntime Method</span></span>

<span data-ttu-id="2a2a3-104">특정 버전의 CLR (공용 언어 런타임)에 해당 하는 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-104">Gets the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="2a2a3-105">이 메서드는 [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) 플래그와 함께 사용 되는 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-105">This method supersedes the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a2a3-106">구문</span><span class="sxs-lookup"><span data-stu-id="2a2a3-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a2a3-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a2a3-107">Parameters</span></span>  

 `pwzVersion`  
 <span data-ttu-id="2a2a3-108">진행 메타 데이터에 저장 된 .NET Framework 컴파일 버전 ("v *A*" 형식)입니다. *B*[.*X*] ".</span><span class="sxs-lookup"><span data-stu-id="2a2a3-108">[in] The .NET Framework compilation version stored in the metadata, in the format "v *A*.*B*[.*X*]".</span></span> <span data-ttu-id="2a2a3-109">*A*, *B* 및 *X* 는 주 버전, 부 버전 및 빌드 번호에 해당 하는 10 진수입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a2a3-110">이 매개 변수는 C:\windows\ microsoft.net \framework 또는 C:\Windows\Microsoft.NET\Framework64. 아래에 표시 되는 .NET Framework 버전의 디렉터리 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-110">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="2a2a3-111">예제 값은 "v v1.0.3705", "v 1.1.4322", "v 2.0.50727" 및 "v 4.0입니다. *X*", 여기서 *x* 는 설치 된 빌드 번호에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-111">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="2a2a3-112">"V" 접두사는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-112">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="2a2a3-113">진행 원하는 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-113">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="2a2a3-114">현재이 매개 변수에 사용할 수 있는 유일한 값은 IID_ICLRRuntimeInfo입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-114">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="2a2a3-115">제한이 요청 된 런타임에 해당 하는 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-115">[out] A pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a2a3-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="2a2a3-116">Return Value</span></span>  

 <span data-ttu-id="2a2a3-117">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-117">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2a2a3-118">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a2a3-118">HRESULT</span></span>|<span data-ttu-id="2a2a3-119">설명</span><span class="sxs-lookup"><span data-stu-id="2a2a3-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a2a3-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a2a3-120">S_OK</span></span>|<span data-ttu-id="2a2a3-121">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="2a2a3-122">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="2a2a3-122">E_POINTER</span></span>|<span data-ttu-id="2a2a3-123">`pwzVersion` 또는 `ppRuntime`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-123">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a2a3-124">설명</span><span class="sxs-lookup"><span data-stu-id="2a2a3-124">Remarks</span></span>  

 <span data-ttu-id="2a2a3-125">이 메서드는 [ICorRuntimeHost](icorruntimehost-interface.md) 인터페이스 및 사용 되지 않는 함수와 같은 레거시 함수와 같은 레거시 인터페이스와 일관 되 게 상호 작용 `CorBindTo*` 합니다 (.NET FRAMEWORK 2.0 호스팅 API에서 [사용 되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="2a2a3-125">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="2a2a3-126">즉, 레거시 API를 사용 하 여 로드 된 런타임이 새 API에 표시 되 고 새 API를 사용 하 여 로드 된 런타임이 레거시 API에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-126">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a2a3-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a2a3-127">Requirements</span></span>  

 <span data-ttu-id="2a2a3-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a2a3-129">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="2a2a3-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2a2a3-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a2a3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a2a3-131">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a2a3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a2a3-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a2a3-132">See also</span></span>

- [<span data-ttu-id="2a2a3-133">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a2a3-133">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="2a2a3-134">사용되지 않는 CLR 호스팅 인터페이스 및 Coclass</span><span class="sxs-lookup"><span data-stu-id="2a2a3-134">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="2a2a3-135">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a2a3-135">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="2a2a3-136">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="2a2a3-136">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="2a2a3-137">호스팅</span><span class="sxs-lookup"><span data-stu-id="2a2a3-137">Hosting</span></span>](index.md)
