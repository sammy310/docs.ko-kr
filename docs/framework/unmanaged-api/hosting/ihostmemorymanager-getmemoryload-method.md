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
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176281"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="5b084-102">IHostMemoryManager::GetMemoryLoad 메서드</span><span class="sxs-lookup"><span data-stu-id="5b084-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="5b084-103">호스트에서 보고한 대로 현재 사용 중인 실제 메모리의 양을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b084-104">구문</span><span class="sxs-lookup"><span data-stu-id="5b084-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b084-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b084-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="5b084-106">【아웃】 현재 사용 중인 총 실제 메모리의 대략적인 백분율에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="5b084-107">【아웃】 공통 언어 런타임(CLR)에서 사용할 수 있는 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b084-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="5b084-108">Return Value</span></span>  
  
|<span data-ttu-id="5b084-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b084-109">HRESULT</span></span>|<span data-ttu-id="5b084-110">Description</span><span class="sxs-lookup"><span data-stu-id="5b084-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b084-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b084-111">S_OK</span></span>|<span data-ttu-id="5b084-112">`GetMemoryLoad`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="5b084-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5b084-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5b084-114">CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5b084-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5b084-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5b084-116">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-116">The call timed out.</span></span>|  
|<span data-ttu-id="5b084-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5b084-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5b084-118">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5b084-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5b084-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5b084-120">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5b084-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5b084-121">E_FAIL</span></span>|<span data-ttu-id="5b084-122">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5b084-123">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5b084-124">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b084-125">설명</span><span class="sxs-lookup"><span data-stu-id="5b084-125">Remarks</span></span>  
 <span data-ttu-id="5b084-126">`GetMemoryLoad`Win32 `GlobalMemoryStatus` 함수를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="5b084-127">`pMemoryLoad` 값은 에서 반환된 `dwMemoryLoad` 구조의 `MEMORYSTATUS` 필드와 `GlobalMemoryStatus`동일합니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="5b084-128">런타임은 반환 값을 가비지 수집기의 추론값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="5b084-129">예를 들어 호스트가 대부분의 메모리가 사용 중이라고 보고하는 경우 가비지 수집기는 잠재적으로 사용 가능해질 수 있는 메모리 양을 늘리기 위해 여러 세대에서 수집하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b084-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b084-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b084-130">Requirements</span></span>  
 <span data-ttu-id="5b084-131">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b084-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b084-132">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="5b084-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b084-133">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5b084-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b084-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b084-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b084-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b084-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="5b084-136">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b084-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
