---
title: ICLRRuntimeHost::SetHostControl 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 68b06a2840de277bdaed1dc9ce0b51e6b363c897
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120459"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="c3ff4-102">ICLRRuntimeHost::SetHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="c3ff4-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="c3ff4-103">CLR (공용 언어 런타임)에서 호스트의 [IHostControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)구현을 가져오는 데 사용할 수 있는 인터페이스 포인터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3ff4-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3ff4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3ff4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3ff4-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="c3ff4-106">진행 호스트의 [IHostControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)구현에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3ff4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c3ff4-107">Return Value</span></span>  
  
|<span data-ttu-id="c3ff4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3ff4-108">HRESULT</span></span>|<span data-ttu-id="c3ff4-109">설명</span><span class="sxs-lookup"><span data-stu-id="c3ff4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3ff4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3ff4-110">S_OK</span></span>|<span data-ttu-id="c3ff4-111">`SetHostControl` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="c3ff4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c3ff4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c3ff4-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c3ff4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c3ff4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c3ff4-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-115">The call timed out.</span></span>|  
|<span data-ttu-id="c3ff4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c3ff4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c3ff4-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c3ff4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c3ff4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c3ff4-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c3ff4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c3ff4-120">E_FAIL</span></span>|<span data-ttu-id="c3ff4-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c3ff4-122">메서드가 E_FAIL을 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c3ff4-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c3ff4-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="c3ff4-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="c3ff4-125">CLR이 이미 초기화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3ff4-126">주의</span><span class="sxs-lookup"><span data-stu-id="c3ff4-126">Remarks</span></span>  
 <span data-ttu-id="c3ff4-127">CLR이 초기화 되기 전에, 즉 [Start 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 를 호출 하거나 [메타 데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)를 사용 하기 전에 `SetHostControl`를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="c3ff4-128">[CorBindToCurrentRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) 또는 [CorBindToRuntimeEx 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)를 호출한 후 즉시 `SetHostControl`를 호출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3ff4-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3ff4-129">Requirements</span></span>  
 <span data-ttu-id="c3ff4-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3ff4-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c3ff4-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3ff4-132">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff4-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3ff4-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3ff4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ff4-134">참조</span><span class="sxs-lookup"><span data-stu-id="c3ff4-134">See also</span></span>

- [<span data-ttu-id="c3ff4-135">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3ff4-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="c3ff4-136">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3ff4-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
