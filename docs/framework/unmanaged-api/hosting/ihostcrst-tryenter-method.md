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
ms.openlocfilehash: 782a12a47de0196b90de06572520ef5ed36efb26
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804872"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="47cba-102">IHostCrst::TryEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="47cba-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="47cba-103">현재 [IHostCrst](ihostcrst-interface.md) 인스턴스로 표시 되는 임계 영역을 입력 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-103">Attempts to enter the critical section represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47cba-104">구문</span><span class="sxs-lookup"><span data-stu-id="47cba-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47cba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47cba-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="47cba-106">진행 작업이 차단 될 경우 호스트가 수행할 동작을 나타내는 [WAIT_OPTION](wait-option-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="47cba-107">[out] `true` 임계 영역을 입력할 수 있으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47cba-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="47cba-108">Return Value</span></span>  
  
|<span data-ttu-id="47cba-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47cba-109">HRESULT</span></span>|<span data-ttu-id="47cba-110">Description</span><span class="sxs-lookup"><span data-stu-id="47cba-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47cba-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="47cba-111">S_OK</span></span>|<span data-ttu-id="47cba-112">`TryEnter`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="47cba-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="47cba-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="47cba-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="47cba-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47cba-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="47cba-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-116">The call timed out.</span></span>|  
|<span data-ttu-id="47cba-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="47cba-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="47cba-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="47cba-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="47cba-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="47cba-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="47cba-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="47cba-121">E_FAIL</span></span>|<span data-ttu-id="47cba-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="47cba-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="47cba-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47cba-125">설명</span><span class="sxs-lookup"><span data-stu-id="47cba-125">Remarks</span></span>  
 <span data-ttu-id="47cba-126">`TryEnter`즉시 반환 하 고 호출 스레드가 임계 영역에 들어간 지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="47cba-127">이 메서드는 Wind32 함수를 미러링합니다 `TryEnterCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="47cba-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47cba-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47cba-128">Requirements</span></span>  
 <span data-ttu-id="47cba-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47cba-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47cba-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="47cba-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47cba-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47cba-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47cba-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47cba-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47cba-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47cba-133">See also</span></span>

- [<span data-ttu-id="47cba-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47cba-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="47cba-135">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47cba-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="47cba-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47cba-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
