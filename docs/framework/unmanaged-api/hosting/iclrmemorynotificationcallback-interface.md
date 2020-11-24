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
ms.openlocfilehash: 5762a354bec485cb382b5460dfd2a337f79bee1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689539"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="8fd7b-102">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8fd7b-102">ICLRMemoryNotificationCallback Interface</span></span>

<span data-ttu-id="8fd7b-103">호스트에서 Win32 함수와 유사한 방법을 사용 하 여 메모리 압력 상태를 보고할 수 있습니다 `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="8fd7b-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8fd7b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="8fd7b-104">Methods</span></span>  
  
|<span data-ttu-id="8fd7b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8fd7b-105">Method</span></span>|<span data-ttu-id="8fd7b-106">설명</span><span class="sxs-lookup"><span data-stu-id="8fd7b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8fd7b-107">OnMemoryNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="8fd7b-107">OnMemoryNotification Method</span></span>](iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="8fd7b-108">컴퓨터의 메모리 로드를 CLR (공용 언어 런타임)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8fd7b-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fd7b-109">설명</span><span class="sxs-lookup"><span data-stu-id="8fd7b-109">Remarks</span></span>  

 <span data-ttu-id="8fd7b-110">호스트는 인터페이스를 사용 하 여 `ICLRMemoryNotificationCallback` CLR의 사용 가능한 메모리 리소스를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd7b-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fd7b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd7b-111">Requirements</span></span>  

 <span data-ttu-id="8fd7b-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd7b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fd7b-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8fd7b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8fd7b-114">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fd7b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8fd7b-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fd7b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd7b-116">참조</span><span class="sxs-lookup"><span data-stu-id="8fd7b-116">See also</span></span>

- [<span data-ttu-id="8fd7b-117">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8fd7b-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="8fd7b-118">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8fd7b-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
