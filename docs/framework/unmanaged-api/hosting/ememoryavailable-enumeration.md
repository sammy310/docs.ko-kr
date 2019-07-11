---
title: EMemoryAvailable 열거형
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76fc5f578e6da731ffd6406344d00cda8b57f493
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772402"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="c865b-102">EMemoryAvailable 열거형</span><span class="sxs-lookup"><span data-stu-id="c865b-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="c865b-103">컴퓨터의 사용 가능한 실제 메모리의 크기를 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c865b-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="c865b-104">이러한 값을 이벤트에 메모리에서 반환 하는 상위 및 하위 논리적으로 매핑할는 `CreateMemoryResourceNotification` Windows api에서 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c865b-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c865b-105">구문</span><span class="sxs-lookup"><span data-stu-id="c865b-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="c865b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c865b-106">Members</span></span>  
  
|<span data-ttu-id="c865b-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c865b-107">Member</span></span>|<span data-ttu-id="c865b-108">Description</span><span class="sxs-lookup"><span data-stu-id="c865b-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="c865b-109">다양 한 실제 메모리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c865b-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="c865b-110">매우 작은 실제 메모리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c865b-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="c865b-111">사용 가능한 실제 메모리를 보통 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c865b-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c865b-112">설명</span><span class="sxs-lookup"><span data-stu-id="c865b-112">Remarks</span></span>  
 <span data-ttu-id="c865b-113">에 대 한 호출을 사용 하는 CLR (공용 언어 런타임)에서 호스트에서이 값은 전달 된 [iclrmemorynotificationcallback:: Onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c865b-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c865b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c865b-114">Requirements</span></span>  
 <span data-ttu-id="c865b-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c865b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c865b-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c865b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c865b-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c865b-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c865b-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c865b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c865b-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="c865b-119">See also</span></span>

- [<span data-ttu-id="c865b-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="c865b-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
