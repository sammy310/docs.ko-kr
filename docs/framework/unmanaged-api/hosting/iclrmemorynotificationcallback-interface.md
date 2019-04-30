---
title: ICLRMemoryNotificationCallback 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c98ece9d60571034f3298f15897b10c4d8fb06f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948553"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="08caa-102">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08caa-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="08caa-103">호스트가 Win32의 비슷한 방법을 사용 하 여 메모리 부족 상태를 보고할 수 있도록 `CreateMemoryResourceNotification` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="08caa-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08caa-104">메서드</span><span class="sxs-lookup"><span data-stu-id="08caa-104">Methods</span></span>  
  
|<span data-ttu-id="08caa-105">메서드</span><span class="sxs-lookup"><span data-stu-id="08caa-105">Method</span></span>|<span data-ttu-id="08caa-106">설명</span><span class="sxs-lookup"><span data-stu-id="08caa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08caa-107">OnMemoryNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="08caa-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="08caa-108">컴퓨터의 메모리 로드 된 CLR (공용 언어 런타임을)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="08caa-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08caa-109">설명</span><span class="sxs-lookup"><span data-stu-id="08caa-109">Remarks</span></span>  
 <span data-ttu-id="08caa-110">호스트가 사용 하는 `ICLRMemoryNotificationCallback` 는 CLR 메모리 리소스를 해제 하는 요청에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="08caa-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08caa-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08caa-111">Requirements</span></span>  
 <span data-ttu-id="08caa-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="08caa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08caa-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08caa-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08caa-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="08caa-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08caa-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08caa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08caa-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="08caa-116">See also</span></span>

- [<span data-ttu-id="08caa-117">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08caa-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="08caa-118">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08caa-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
