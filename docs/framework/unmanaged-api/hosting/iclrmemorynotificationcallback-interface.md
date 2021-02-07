---
description: '자세히 알아보기: ICLRMemoryNotificationCallback 인터페이스'
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
ms.openlocfilehash: 46e53cdf0b7f797b8945237d47fc3b521b08ddb7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689228"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="630f1-103">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="630f1-103">ICLRMemoryNotificationCallback Interface</span></span>

<span data-ttu-id="630f1-104">호스트에서 Win32 함수와 유사한 방법을 사용 하 여 메모리 압력 상태를 보고할 수 있습니다 `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="630f1-104">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="630f1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="630f1-105">Methods</span></span>  
  
|<span data-ttu-id="630f1-106">메서드</span><span class="sxs-lookup"><span data-stu-id="630f1-106">Method</span></span>|<span data-ttu-id="630f1-107">설명</span><span class="sxs-lookup"><span data-stu-id="630f1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="630f1-108">OnMemoryNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="630f1-108">OnMemoryNotification Method</span></span>](iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="630f1-109">컴퓨터의 메모리 로드를 CLR (공용 언어 런타임)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="630f1-109">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="630f1-110">설명</span><span class="sxs-lookup"><span data-stu-id="630f1-110">Remarks</span></span>  

 <span data-ttu-id="630f1-111">호스트는 인터페이스를 사용 하 여 `ICLRMemoryNotificationCallback` CLR의 사용 가능한 메모리 리소스를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="630f1-111">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="630f1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="630f1-112">Requirements</span></span>  

 <span data-ttu-id="630f1-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="630f1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="630f1-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="630f1-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="630f1-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="630f1-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="630f1-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="630f1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="630f1-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="630f1-117">See also</span></span>

- [<span data-ttu-id="630f1-118">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="630f1-118">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="630f1-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="630f1-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
