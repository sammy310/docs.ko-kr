---
title: IHostCrst::Leave 메서드
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d60cdee0a5357f7e117dc902b073049f3bbaea9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198480"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="f11b2-102">IHostCrst::Leave 메서드</span><span class="sxs-lookup"><span data-stu-id="f11b2-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="f11b2-103">현재 인스턴스에 의해 표현 되는 중요 섹션을 벗어날 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b2-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f11b2-104">구문</span><span class="sxs-lookup"><span data-stu-id="f11b2-104">Syntax</span></span>  
  
```  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f11b2-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="f11b2-105">Return Value</span></span>  
  
|<span data-ttu-id="f11b2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f11b2-106">HRESULT</span></span>|<span data-ttu-id="f11b2-107">설명</span><span class="sxs-lookup"><span data-stu-id="f11b2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f11b2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f11b2-108">S_OK</span></span>|`Leave` <span data-ttu-id="f11b2-109">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b2-109">returned successfully.</span></span>|  
|<span data-ttu-id="f11b2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f11b2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f11b2-111">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b2-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f11b2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f11b2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f11b2-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b2-113">The call timed out.</span></span>|  
|<span data-ttu-id="f11b2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f11b2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f11b2-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f11b2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f11b2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f11b2-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f11b2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f11b2-118">E_FAIL</span></span>|<span data-ttu-id="f11b2-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f11b2-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f11b2-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f11b2-122">설명</span><span class="sxs-lookup"><span data-stu-id="f11b2-122">Remarks</span></span>  
 `Leave` <span data-ttu-id="f11b2-123">CLR 호스트의 스레딩 구현을 사용 하는 대신 해당 Win32와 직접 통신 하도록 허용 `LeaveCriticalSection` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="f11b2-123">allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="f11b2-124">현재 임계의 소유권을 갖습니다 하는 스레드 `IHostCrst` 인스턴스를 호출 해야 `Leave` 되 면 각 시간에 대 한 중요 한 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="f11b2-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f11b2-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f11b2-125">Requirements</span></span>  
 <span data-ttu-id="f11b2-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f11b2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f11b2-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f11b2-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f11b2-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f11b2-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f11b2-129">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f11b2-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f11b2-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="f11b2-130">See also</span></span>

- [<span data-ttu-id="f11b2-131">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f11b2-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="f11b2-132">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f11b2-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="f11b2-133">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f11b2-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
