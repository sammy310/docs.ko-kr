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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e443ec3f743d56f0fe7e4e1c794f16bab2db8314
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763969"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="a40d1-102">IHostAutoEvent::Set 메서드</span><span class="sxs-lookup"><span data-stu-id="a40d1-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="a40d1-103">에서는 현재 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) 신호를 받은 상태 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="a40d1-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a40d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="a40d1-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a40d1-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="a40d1-105">Return Value</span></span>  
  
|<span data-ttu-id="a40d1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a40d1-106">HRESULT</span></span>|<span data-ttu-id="a40d1-107">Description</span><span class="sxs-lookup"><span data-stu-id="a40d1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a40d1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a40d1-108">S_OK</span></span>|<span data-ttu-id="a40d1-109">`Set` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40d1-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="a40d1-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a40d1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a40d1-111">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a40d1-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a40d1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a40d1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a40d1-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a40d1-113">The call timed out.</span></span>|  
|<span data-ttu-id="a40d1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a40d1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a40d1-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a40d1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a40d1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a40d1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a40d1-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a40d1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a40d1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a40d1-118">E_FAIL</span></span>|<span data-ttu-id="a40d1-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a40d1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a40d1-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a40d1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a40d1-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40d1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a40d1-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a40d1-122">Requirements</span></span>  
 <span data-ttu-id="a40d1-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a40d1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a40d1-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a40d1-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a40d1-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a40d1-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a40d1-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a40d1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a40d1-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="a40d1-127">See also</span></span>

- [<span data-ttu-id="a40d1-128">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a40d1-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a40d1-129">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a40d1-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="a40d1-130">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a40d1-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="a40d1-131">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a40d1-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
