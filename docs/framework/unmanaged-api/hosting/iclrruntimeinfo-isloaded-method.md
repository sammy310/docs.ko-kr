---
title: ICLRRuntimeInfo::IsLoaded 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 156906a84013148a4afe3d0687e8d136ca819c8a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584412"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="10ed6-102">ICLRRuntimeInfo::IsLoaded 메서드</span><span class="sxs-lookup"><span data-stu-id="10ed6-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="10ed6-103">CLR (공용 언어 런타임)에 연결 된 여부를 나타내는 합니다 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스는 프로세스에 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10ed6-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="10ed6-104">시작 하지 않고 런타임에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed6-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ed6-105">구문</span><span class="sxs-lookup"><span data-stu-id="10ed6-105">Syntax</span></span>  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10ed6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10ed6-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="10ed6-107">[in] 프로세스 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="10ed6-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="10ed6-108">[out] `true` CLR이 고, 그렇지 않으면 프로세스에 로드 하는 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="10ed6-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10ed6-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="10ed6-109">Return Value</span></span>  
 <span data-ttu-id="10ed6-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="10ed6-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="10ed6-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10ed6-111">HRESULT</span></span>|<span data-ttu-id="10ed6-112">설명</span><span class="sxs-lookup"><span data-stu-id="10ed6-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10ed6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="10ed6-113">S_OK</span></span>|<span data-ttu-id="10ed6-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed6-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="10ed6-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="10ed6-115">E_POINTER</span></span>|<span data-ttu-id="10ed6-116">`pbLoaded`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="10ed6-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10ed6-117">설명</span><span class="sxs-lookup"><span data-stu-id="10ed6-117">Remarks</span></span>  
 <span data-ttu-id="10ed6-118">이 메서드는 이전 버전과 호환성이 다음 함수 및 인터페이스를 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="10ed6-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="10ed6-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) (.NET Framework 버전 1 호스팅 API)의 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="10ed6-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="10ed6-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) (호스팅 API는.NET Framework 2.0)의 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="10ed6-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="10ed6-121">사용 되지 않음 `CorBindTo*` 함수 (참조 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) 호스팅 API는.NET Framework 2.0에서).</span><span class="sxs-lookup"><span data-stu-id="10ed6-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="10ed6-122">호스트 사용 되지 않는 중 하나를 호출할 수 있습니다 `CorBindTo*` 와 같은 함수를 [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) 함수를 CLR의 특정 버전을 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="10ed6-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="10ed6-123">호스트 호출할 수는 [iclrmetahost:: Getruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) 메서드를 가져올 동일한 버전 번호를 지정 하 고는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="10ed6-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="10ed6-124">호스트 한 다음 호출 하는 경우는 `IsLoaded` 메서드는 반환 된 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스 `pbLoaded` 반환 `true`고, 그렇지 않으면 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="10ed6-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10ed6-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10ed6-125">Requirements</span></span>  
 <span data-ttu-id="10ed6-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="10ed6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10ed6-127">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="10ed6-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="10ed6-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="10ed6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10ed6-129">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10ed6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ed6-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="10ed6-130">See also</span></span>

- [<span data-ttu-id="10ed6-131">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10ed6-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="10ed6-132">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10ed6-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="10ed6-133">호스팅</span><span class="sxs-lookup"><span data-stu-id="10ed6-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
