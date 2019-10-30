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
ms.openlocfilehash: aec3c5f140df7eab10ea2bfa33634a4d853adcb0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134299"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="aa03b-102">EMemoryAvailable 열거형</span><span class="sxs-lookup"><span data-stu-id="aa03b-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="aa03b-103">컴퓨터에서 사용 가능한 실제 메모리의 양을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa03b-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="aa03b-104">이러한 값은 Windows API의 `CreateMemoryResourceNotification` 함수에서 반환 되는 높은 메모리와 낮은 메모리에 대 한 이벤트에 논리적으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa03b-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa03b-105">구문</span><span class="sxs-lookup"><span data-stu-id="aa03b-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="aa03b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="aa03b-106">Members</span></span>  
  
|<span data-ttu-id="aa03b-107">멤버</span><span class="sxs-lookup"><span data-stu-id="aa03b-107">Member</span></span>|<span data-ttu-id="aa03b-108">설명</span><span class="sxs-lookup"><span data-stu-id="aa03b-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="aa03b-109">충분 한 실제 메모리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa03b-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="aa03b-110">거의 실제 메모리를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa03b-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="aa03b-111">사용 가능한 실제 메모리가 중립입니다.</span><span class="sxs-lookup"><span data-stu-id="aa03b-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa03b-112">주의</span><span class="sxs-lookup"><span data-stu-id="aa03b-112">Remarks</span></span>  
 <span data-ttu-id="aa03b-113">이 값은 [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) 메서드를 호출 하 여 호스트에서 CLR (공용 언어 런타임)로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa03b-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa03b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa03b-114">Requirements</span></span>  
 <span data-ttu-id="aa03b-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa03b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa03b-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="aa03b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa03b-117">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="aa03b-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa03b-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa03b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa03b-119">참조</span><span class="sxs-lookup"><span data-stu-id="aa03b-119">See also</span></span>

- [<span data-ttu-id="aa03b-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="aa03b-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
