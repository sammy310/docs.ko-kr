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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ac28f28d4d284ba26fadd46e53ebeb8e5b5f3cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139583"
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="89c2b-102">WAIT_OPTION 열거형</span><span class="sxs-lookup"><span data-stu-id="89c2b-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="89c2b-103">작업을 호스트 하는 경우 공용 언어 런타임 (CLR) 블록에서 요청한 작업 수행 해야 여부를 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="89c2b-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="89c2b-104">Syntax</span></span>  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="89c2b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="89c2b-105">Members</span></span>  
  
|<span data-ttu-id="89c2b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="89c2b-106">Member</span></span>|<span data-ttu-id="89c2b-107">설명</span><span class="sxs-lookup"><span data-stu-id="89c2b-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="89c2b-108">작업은 CLR에서 호출 하는 경우 다시 시작 될 호스트에 알립니다. 합니다 [ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="89c2b-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="89c2b-109">스레드가 차단 되는 경우 현재 OS 스레드에서 메시지를 펌프 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="89c2b-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="89c2b-110">에이 값을 지정 하는 런타임에서 <xref:System.Threading.ApartmentState.STA> 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="89c2b-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="89c2b-111">호스트에서 지정 된 동기화 요청을 분리할 수 없는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="89c2b-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="89c2b-112">호스트를 반환할 수 없습니다. 즉, `HOST_E_DEADLOCK`합니다.</span><span class="sxs-lookup"><span data-stu-id="89c2b-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89c2b-113">설명</span><span class="sxs-lookup"><span data-stu-id="89c2b-113">Remarks</span></span>  
 <span data-ttu-id="89c2b-114">합니다 [ihosttaskmanager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) 하 고 [ihosttaskmanager:: Switchtotask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) 메서드는 모두 이러한 종류의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89c2b-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89c2b-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89c2b-115">Requirements</span></span>  
 <span data-ttu-id="89c2b-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="89c2b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89c2b-117">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="89c2b-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89c2b-118">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89c2b-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89c2b-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89c2b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c2b-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="89c2b-120">See also</span></span>

- [<span data-ttu-id="89c2b-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="89c2b-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
