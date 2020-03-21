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
ms.openlocfilehash: 0073a532f680d8764ec9e76ea22326a630457043
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176437"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="1b2ca-102">EMemoryAvailable 열거형</span><span class="sxs-lookup"><span data-stu-id="1b2ca-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="1b2ca-103">컴퓨터에서 사용 가능한 실제 메모리의 양을 나타내는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="1b2ca-104">이러한 값은 Windows API의 함수에서 반환되는 `CreateMemoryResourceNotification` 높고 낮은 메모리에 대한 이벤트에 논리적으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b2ca-105">구문</span><span class="sxs-lookup"><span data-stu-id="1b2ca-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="1b2ca-106">구성원</span><span class="sxs-lookup"><span data-stu-id="1b2ca-106">Members</span></span>  
  
|<span data-ttu-id="1b2ca-107">멤버</span><span class="sxs-lookup"><span data-stu-id="1b2ca-107">Member</span></span>|<span data-ttu-id="1b2ca-108">Description</span><span class="sxs-lookup"><span data-stu-id="1b2ca-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="1b2ca-109">실제 메모리를 많이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="1b2ca-110">실제 메모리를 사용할 수 있는 것은 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="1b2ca-111">사용 가능한 실제 메모리는 중립적입니다.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b2ca-112">설명</span><span class="sxs-lookup"><span data-stu-id="1b2ca-112">Remarks</span></span>  
 <span data-ttu-id="1b2ca-113">이 값은 [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) 메서드에 대 한 호출을 사용 하 여 공통 언어 런타임 (CLR)에 호스트에 의해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b2ca-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b2ca-114">Requirements</span></span>  
 <span data-ttu-id="1b2ca-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b2ca-116">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="1b2ca-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b2ca-117">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1b2ca-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b2ca-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b2ca-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b2ca-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b2ca-119">See also</span></span>

- [<span data-ttu-id="1b2ca-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="1b2ca-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
