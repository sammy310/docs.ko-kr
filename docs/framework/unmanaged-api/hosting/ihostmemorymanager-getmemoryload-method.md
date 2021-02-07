---
description: '자세히 알아보기: IHostMemoryManager:: GetMemoryLoad 메서드'
title: IHostMemoryManager::GetMemoryLoad 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
ms.openlocfilehash: 82288e6a705b014c2768c75e15376f7e6a0af428
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707847"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="d72c4-103">IHostMemoryManager::GetMemoryLoad 메서드</span><span class="sxs-lookup"><span data-stu-id="d72c4-103">IHostMemoryManager::GetMemoryLoad Method</span></span>

<span data-ttu-id="d72c4-104">호스트에서 보고 한 대로 현재 사용 되 고 있으므로 사용할 수 없는 실제 메모리의 양을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-104">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d72c4-105">구문</span><span class="sxs-lookup"><span data-stu-id="d72c4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d72c4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d72c4-106">Parameters</span></span>  

 `pMemoryLoad`  
 <span data-ttu-id="d72c4-107">제한이 현재 사용 중인 총 실제 메모리의 대략적인 백분율에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-107">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="d72c4-108">제한이 CLR (공용 언어 런타임)에 사용할 수 있는 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-108">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d72c4-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="d72c4-109">Return Value</span></span>  
  
|<span data-ttu-id="d72c4-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d72c4-110">HRESULT</span></span>|<span data-ttu-id="d72c4-111">설명</span><span class="sxs-lookup"><span data-stu-id="d72c4-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d72c4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d72c4-112">S_OK</span></span>|<span data-ttu-id="d72c4-113">`GetMemoryLoad` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-113">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="d72c4-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d72c4-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d72c4-115">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d72c4-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d72c4-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d72c4-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-117">The call timed out.</span></span>|  
|<span data-ttu-id="d72c4-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d72c4-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d72c4-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d72c4-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d72c4-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d72c4-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d72c4-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d72c4-122">E_FAIL</span></span>|<span data-ttu-id="d72c4-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d72c4-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d72c4-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d72c4-126">설명</span><span class="sxs-lookup"><span data-stu-id="d72c4-126">Remarks</span></span>  

 <span data-ttu-id="d72c4-127">`GetMemoryLoad` Win32 함수를 래핑합니다 `GlobalMemoryStatus` .</span><span class="sxs-lookup"><span data-stu-id="d72c4-127">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="d72c4-128">의 값은 `pMemoryLoad` `dwMemoryLoad` 에서 반환 된 구조체의 필드에 해당 하는 값입니다 `MEMORYSTATUS` `GlobalMemoryStatus` .</span><span class="sxs-lookup"><span data-stu-id="d72c4-128">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="d72c4-129">런타임은 반환 값을 가비지 수집기에 대 한 추론으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-129">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="d72c4-130">예를 들어 호스트가 대다수의 메모리를 사용 하 고 있음을 보고 하는 경우 가비지 수집기는 여러 세대에서 수집 하도록 선택 하 여 잠재적으로 사용 가능 해질 수 있는 메모리 양을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-130">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d72c4-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d72c4-131">Requirements</span></span>  

 <span data-ttu-id="d72c4-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d72c4-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d72c4-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d72c4-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d72c4-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72c4-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d72c4-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d72c4-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d72c4-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d72c4-136">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="d72c4-137">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d72c4-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
