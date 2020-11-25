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
ms.openlocfilehash: 32483be43d4d4fe9d185c091e15a13c6feb95600
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728825"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="100f1-102">ICLRRuntimeHost::SetHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="100f1-102">ICLRRuntimeHost::SetHostControl Method</span></span>

<span data-ttu-id="100f1-103">CLR (공용 언어 런타임)에서 호스트의 [IHostControl 인터페이스](ihostcontrol-interface.md)구현을 가져오는 데 사용할 수 있는 인터페이스 포인터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="100f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="100f1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="100f1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="100f1-105">Parameters</span></span>  

 `pHostControl`  
 <span data-ttu-id="100f1-106">진행 호스트의 [IHostControl 인터페이스](ihostcontrol-interface.md)구현에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="100f1-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="100f1-107">Return Value</span></span>  
  
|<span data-ttu-id="100f1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="100f1-108">HRESULT</span></span>|<span data-ttu-id="100f1-109">설명</span><span class="sxs-lookup"><span data-stu-id="100f1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="100f1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="100f1-110">S_OK</span></span>|<span data-ttu-id="100f1-111">`SetHostControl` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="100f1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="100f1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="100f1-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="100f1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="100f1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="100f1-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-115">The call timed out.</span></span>|  
|<span data-ttu-id="100f1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="100f1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="100f1-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="100f1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="100f1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="100f1-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="100f1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="100f1-120">E_FAIL</span></span>|<span data-ttu-id="100f1-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="100f1-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="100f1-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="100f1-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="100f1-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="100f1-125">CLR이 이미 초기화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="100f1-126">설명</span><span class="sxs-lookup"><span data-stu-id="100f1-126">Remarks</span></span>  

 <span data-ttu-id="100f1-127">CLR을 초기화 하기 전에를 호출 해야 합니다 `SetHostControl` . 즉, [시작 메서드](iclrruntimehost-start-method.md) 를 호출 하거나 [메타 데이터 인터페이스](../metadata/metadata-interfaces.md)를 사용 하기 전에를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="100f1-128">`SetHostControl` [CorBindToCurrentRuntime 함수](corbindtocurrentruntime-function.md) 또는 [CorBindToRuntimeEx 함수](corbindtoruntimeex-function.md)를 호출한 후 즉시 호출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="100f1-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="100f1-129">Requirements</span></span>  

 <span data-ttu-id="100f1-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="100f1-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="100f1-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="100f1-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="100f1-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="100f1-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="100f1-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="100f1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="100f1-134">참조</span><span class="sxs-lookup"><span data-stu-id="100f1-134">See also</span></span>

- [<span data-ttu-id="100f1-135">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="100f1-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="100f1-136">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="100f1-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
