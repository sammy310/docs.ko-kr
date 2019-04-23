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
ms.openlocfilehash: 5af9f55bdcfe23f0b2a051b33cb1280f312820a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227017"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="7e3c6-102">IHostAutoEvent::Set 메서드</span><span class="sxs-lookup"><span data-stu-id="7e3c6-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="7e3c6-103">에서는 현재 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) 신호를 받은 상태 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e3c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e3c6-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7e3c6-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="7e3c6-105">Return Value</span></span>  
  
|<span data-ttu-id="7e3c6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e3c6-106">HRESULT</span></span>|<span data-ttu-id="7e3c6-107">설명</span><span class="sxs-lookup"><span data-stu-id="7e3c6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e3c6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e3c6-108">S_OK</span></span>|<span data-ttu-id="7e3c6-109">`Set` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="7e3c6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e3c6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e3c6-111">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e3c6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7e3c6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7e3c6-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-113">The call timed out.</span></span>|  
|<span data-ttu-id="7e3c6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7e3c6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7e3c6-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7e3c6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7e3c6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7e3c6-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7e3c6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e3c6-118">E_FAIL</span></span>|<span data-ttu-id="7e3c6-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e3c6-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7e3c6-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e3c6-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e3c6-122">Requirements</span></span>  
 <span data-ttu-id="7e3c6-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e3c6-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7e3c6-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e3c6-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7e3c6-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e3c6-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e3c6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e3c6-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="7e3c6-127">See also</span></span>

- [<span data-ttu-id="7e3c6-128">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e3c6-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="7e3c6-129">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e3c6-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="7e3c6-130">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e3c6-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="7e3c6-131">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e3c6-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
