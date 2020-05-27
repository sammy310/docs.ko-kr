---
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
ms.openlocfilehash: 73d9ae865b2c971a4defcacf5bd6505836c74e02
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804500"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="f2ce6-102">IHostMemoryManager::GetMemoryLoad 메서드</span><span class="sxs-lookup"><span data-stu-id="f2ce6-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="f2ce6-103">호스트에서 보고 한 대로 현재 사용 되 고 있으므로 사용할 수 없는 실제 메모리의 양을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ce6-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2ce6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2ce6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2ce6-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="f2ce6-106">제한이 현재 사용 중인 총 실제 메모리의 대략적인 백분율에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="f2ce6-107">제한이 CLR (공용 언어 런타임)에 사용할 수 있는 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2ce6-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="f2ce6-108">Return Value</span></span>  
  
|<span data-ttu-id="f2ce6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2ce6-109">HRESULT</span></span>|<span data-ttu-id="f2ce6-110">Description</span><span class="sxs-lookup"><span data-stu-id="f2ce6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2ce6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2ce6-111">S_OK</span></span>|<span data-ttu-id="f2ce6-112">`GetMemoryLoad`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="f2ce6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f2ce6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f2ce6-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f2ce6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f2ce6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f2ce6-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-116">The call timed out.</span></span>|  
|<span data-ttu-id="f2ce6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f2ce6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f2ce6-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f2ce6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f2ce6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f2ce6-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f2ce6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2ce6-121">E_FAIL</span></span>|<span data-ttu-id="f2ce6-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f2ce6-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f2ce6-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2ce6-125">설명</span><span class="sxs-lookup"><span data-stu-id="f2ce6-125">Remarks</span></span>  
 <span data-ttu-id="f2ce6-126">`GetMemoryLoad`Win32 함수를 래핑합니다 `GlobalMemoryStatus` .</span><span class="sxs-lookup"><span data-stu-id="f2ce6-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="f2ce6-127">의 값은 `pMemoryLoad` `dwMemoryLoad` 에서 반환 된 구조체의 필드에 해당 하는 값입니다 `MEMORYSTATUS` `GlobalMemoryStatus` .</span><span class="sxs-lookup"><span data-stu-id="f2ce6-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="f2ce6-128">런타임은 반환 값을 가비지 수집기에 대 한 추론으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="f2ce6-129">예를 들어 호스트가 대다수의 메모리를 사용 하 고 있음을 보고 하는 경우 가비지 수집기는 여러 세대에서 수집 하도록 선택 하 여 잠재적으로 사용 가능 해질 수 있는 메모리 양을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ce6-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2ce6-130">Requirements</span></span>  
 <span data-ttu-id="f2ce6-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ce6-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f2ce6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2ce6-133">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ce6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2ce6-134">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ce6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ce6-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2ce6-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="f2ce6-136">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2ce6-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
