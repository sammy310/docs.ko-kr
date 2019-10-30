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
ms.openlocfilehash: e0ab16348abbaff00152f2b259ccafdd331174df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136357"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="6f078-102">ICLRRuntimeInfo::IsLoaded 메서드</span><span class="sxs-lookup"><span data-stu-id="6f078-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="6f078-103">[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스와 연결 된 CLR (공용 언어 런타임)이 프로세스에 로드 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="6f078-104">런타임을 시작 하지 않고도 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f078-105">구문</span><span class="sxs-lookup"><span data-stu-id="6f078-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f078-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f078-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="6f078-107">진행 프로세스에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="6f078-108">[out] CLR이 프로세스에 로드 되 면이 고, 그렇지 않으면 `true` 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f078-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="6f078-109">Return Value</span></span>  
 <span data-ttu-id="6f078-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6f078-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f078-111">HRESULT</span></span>|<span data-ttu-id="6f078-112">설명</span><span class="sxs-lookup"><span data-stu-id="6f078-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f078-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f078-113">S_OK</span></span>|<span data-ttu-id="6f078-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="6f078-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6f078-115">E_POINTER</span></span>|<span data-ttu-id="6f078-116">`pbLoaded`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f078-117">주의</span><span class="sxs-lookup"><span data-stu-id="6f078-117">Remarks</span></span>  
 <span data-ttu-id="6f078-118">이 메서드는 다음 함수와 인터페이스와 이전 버전과 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="6f078-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 인터페이스 (.NET Framework 버전 1 호스팅 API)</span><span class="sxs-lookup"><span data-stu-id="6f078-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="6f078-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스 (.NET Framework 2.0 호스팅 API)</span><span class="sxs-lookup"><span data-stu-id="6f078-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="6f078-121">사용 되지 않는 `CorBindTo*` 함수 (.NET Framework 2.0 호스팅 API에서 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="6f078-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="6f078-122">호스트는 [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) 함수와 같은 사용 되지 않는 `CorBindTo*` 함수 중 하나를 호출 하 여 특정 버전의 CLR을 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="6f078-123">그러면 호스트에서 [ICLRMetaHost:: GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) 메서드를 호출 하 고 동일한 버전 번호를 지정 하 여 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="6f078-124">그런 다음 호스트에서 반환 된 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스에 대해 `IsLoaded` 메서드를 호출 하는 경우 `pbLoaded`는 `true`를 반환 합니다. 그렇지 않으면 `false`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f078-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f078-125">Requirements</span></span>  
 <span data-ttu-id="6f078-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f078-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f078-127">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="6f078-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6f078-128">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f078-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f078-129">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f078-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f078-130">참조</span><span class="sxs-lookup"><span data-stu-id="6f078-130">See also</span></span>

- [<span data-ttu-id="6f078-131">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f078-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="6f078-132">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f078-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="6f078-133">호스팅</span><span class="sxs-lookup"><span data-stu-id="6f078-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
