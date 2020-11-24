---
title: IHostAutoEvent::Set 메서드
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
ms.openlocfilehash: facfbb85645f444b010cb1fe1c34bbe94011ac50
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680830"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="dcbbb-102">IHostAutoEvent::Set 메서드</span><span class="sxs-lookup"><span data-stu-id="dcbbb-102">IHostAutoEvent::Set Method</span></span>

<span data-ttu-id="dcbbb-103">현재 [IHostAutoEvent](ihostautoevent-interface.md) 인스턴스를 신호를 받은 상태로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbb-103">Sets the current [IHostAutoEvent](ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcbbb-104">구문</span><span class="sxs-lookup"><span data-stu-id="dcbbb-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="dcbbb-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="dcbbb-105">Return Value</span></span>  
  
|<span data-ttu-id="dcbbb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dcbbb-106">HRESULT</span></span>|<span data-ttu-id="dcbbb-107">설명</span><span class="sxs-lookup"><span data-stu-id="dcbbb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dcbbb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="dcbbb-108">S_OK</span></span>|<span data-ttu-id="dcbbb-109">`Set` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbb-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="dcbbb-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dcbbb-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dcbbb-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbb-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dcbbb-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dcbbb-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dcbbb-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbb-113">The call timed out.</span></span>|  
|<span data-ttu-id="dcbbb-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dcbbb-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dcbbb-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbb-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dcbbb-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dcbbb-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dcbbb-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbb-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dcbbb-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dcbbb-118">E_FAIL</span></span>|<span data-ttu-id="dcbbb-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbb-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dcbbb-120">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbb-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dcbbb-121">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbb-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dcbbb-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dcbbb-122">Requirements</span></span>  

 <span data-ttu-id="dcbbb-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dcbbb-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcbbb-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="dcbbb-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dcbbb-125">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbb-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dcbbb-126">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcbbb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcbbb-127">참조</span><span class="sxs-lookup"><span data-stu-id="dcbbb-127">See also</span></span>

- [<span data-ttu-id="dcbbb-128">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dcbbb-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="dcbbb-129">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dcbbb-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="dcbbb-130">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dcbbb-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="dcbbb-131">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dcbbb-131">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
