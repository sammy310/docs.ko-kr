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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53001d6dfef2813df86dc4bb4f9647900143aae7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469068"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="71bc9-102">IHostMemoryManager::GetMemoryLoad 메서드</span><span class="sxs-lookup"><span data-stu-id="71bc9-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="71bc9-103">현재 사용 중 및 호스트에 의해 보고 된 것 이므로 사용할 수 있는 실제 메모리의 양을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71bc9-104">구문</span><span class="sxs-lookup"><span data-stu-id="71bc9-104">Syntax</span></span>  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71bc9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71bc9-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="71bc9-106">[out] 현재 사용 중인 총 실제 메모리의 대략적인 백분율에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="71bc9-107">[out] CLR (공용 언어 런타임)에 사용 가능한 바이트의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71bc9-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="71bc9-108">Return Value</span></span>  
  
|<span data-ttu-id="71bc9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71bc9-109">HRESULT</span></span>|<span data-ttu-id="71bc9-110">설명</span><span class="sxs-lookup"><span data-stu-id="71bc9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71bc9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="71bc9-111">S_OK</span></span>|<span data-ttu-id="71bc9-112">`GetMemoryLoad` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="71bc9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71bc9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71bc9-114">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71bc9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71bc9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71bc9-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-116">The call timed out.</span></span>|  
|<span data-ttu-id="71bc9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71bc9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71bc9-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71bc9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71bc9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71bc9-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71bc9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71bc9-121">E_FAIL</span></span>|<span data-ttu-id="71bc9-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71bc9-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71bc9-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71bc9-125">설명</span><span class="sxs-lookup"><span data-stu-id="71bc9-125">Remarks</span></span>  
 <span data-ttu-id="71bc9-126">`GetMemoryLoad` Win32 래핑합니다 `GlobalMemoryStatus` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="71bc9-127">값 `pMemoryLoad` 동일 합니다 `dwMemoryLoad` 필드를 `MEMORYSTATUS` 에서 반환 된 구조 `GlobalMemoryStatus`.</span><span class="sxs-lookup"><span data-stu-id="71bc9-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="71bc9-128">런타임은 가비지 수집기에 대 한 휴리스틱으로 반환 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="71bc9-129">예를 들어, 호스트 사용 중인 메모리의 대부분을 보고, 가비지 수집기 사용 가능한 상태가 될 수 있는 메모리 양을 증가 시켜 여러 세대에서 수집 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71bc9-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71bc9-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71bc9-130">Requirements</span></span>  
 <span data-ttu-id="71bc9-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71bc9-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71bc9-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71bc9-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71bc9-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="71bc9-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71bc9-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71bc9-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71bc9-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="71bc9-135">See also</span></span>
- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="71bc9-136">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71bc9-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
