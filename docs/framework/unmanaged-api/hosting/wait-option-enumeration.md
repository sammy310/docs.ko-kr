---
title: WAIT_OPTION 열거형
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 9ecfb551b55551e5f6cc7e7e9ffb55e5a96259ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141508"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="2bfc9-102">WAIT_OPTION 열거형</span><span class="sxs-lookup"><span data-stu-id="2bfc9-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="2bfc9-103">CLR (공용 언어 런타임) 블록에서 요청 된 작업을 수행할 때 호스트가 수행할 동작을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bfc9-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bfc9-104">구문</span><span class="sxs-lookup"><span data-stu-id="2bfc9-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="2bfc9-105">멤버</span><span class="sxs-lookup"><span data-stu-id="2bfc9-105">Members</span></span>  
  
|<span data-ttu-id="2bfc9-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2bfc9-106">Member</span></span>|<span data-ttu-id="2bfc9-107">설명</span><span class="sxs-lookup"><span data-stu-id="2bfc9-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="2bfc9-108">CLR이 [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) 메서드를 호출 하는 경우 작업을 활성화 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2bfc9-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="2bfc9-109">스레드가 차단 되는 경우 현재 OS 스레드에서 메시지를 펌프 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2bfc9-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="2bfc9-110">런타임은 <xref:System.Threading.ApartmentState.STA> 스레드에서만이 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bfc9-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="2bfc9-111">호스트에서 지정 된 동기화 요청을 나눌 수 없음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2bfc9-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="2bfc9-112">즉, 호스트는 `HOST_E_DEADLOCK`을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2bfc9-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bfc9-113">주의</span><span class="sxs-lookup"><span data-stu-id="2bfc9-113">Remarks</span></span>  
 <span data-ttu-id="2bfc9-114">[IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) 및 [IHostTaskManager:: switchtotask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) 메서드는 모두이 형식의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bfc9-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bfc9-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2bfc9-115">Requirements</span></span>  
 <span data-ttu-id="2bfc9-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2bfc9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bfc9-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2bfc9-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2bfc9-118">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2bfc9-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bfc9-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bfc9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bfc9-120">참조</span><span class="sxs-lookup"><span data-stu-id="2bfc9-120">See also</span></span>

- [<span data-ttu-id="2bfc9-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="2bfc9-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
