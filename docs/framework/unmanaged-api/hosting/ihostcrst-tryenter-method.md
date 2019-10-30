---
title: IHostCrst::TryEnter 메서드
ms.date: 03/30/2017
api_name:
- IHostCrst.TryEnter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type:
- apiref
ms.openlocfilehash: f4b40a595bbdea4dd390a42af6a0d4b1a5efa2f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130502"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="669e7-102">IHostCrst::TryEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="669e7-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="669e7-103">현재 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) 인스턴스로 표시 되는 임계 영역을 입력 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="669e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="669e7-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="669e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="669e7-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="669e7-106">진행 작업이 차단 될 경우 호스트에서 수행할 동작을 나타내는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="669e7-107">[out] 임계 영역을 입력할 수 있는지 여부를 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="669e7-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="669e7-108">Return Value</span></span>  
  
|<span data-ttu-id="669e7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="669e7-109">HRESULT</span></span>|<span data-ttu-id="669e7-110">설명</span><span class="sxs-lookup"><span data-stu-id="669e7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="669e7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="669e7-111">S_OK</span></span>|<span data-ttu-id="669e7-112">`TryEnter` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="669e7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="669e7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="669e7-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="669e7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="669e7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="669e7-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-116">The call timed out.</span></span>|  
|<span data-ttu-id="669e7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="669e7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="669e7-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="669e7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="669e7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="669e7-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="669e7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="669e7-121">E_FAIL</span></span>|<span data-ttu-id="669e7-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="669e7-123">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="669e7-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="669e7-125">주의</span><span class="sxs-lookup"><span data-stu-id="669e7-125">Remarks</span></span>  
 <span data-ttu-id="669e7-126">`TryEnter` 즉시 반환 되 고 호출 스레드가 임계 영역에 입력 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="669e7-127">이 메서드는 Wind32 `TryEnterCriticalSection` 함수를 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="669e7-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="669e7-128">Requirements</span></span>  
 <span data-ttu-id="669e7-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="669e7-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="669e7-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="669e7-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="669e7-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="669e7-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="669e7-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="669e7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="669e7-133">참조</span><span class="sxs-lookup"><span data-stu-id="669e7-133">See also</span></span>

- [<span data-ttu-id="669e7-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="669e7-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="669e7-135">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="669e7-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="669e7-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="669e7-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
