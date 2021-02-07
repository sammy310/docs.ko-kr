---
description: '다음에 대 한 자세한 정보: 열거형 WAIT_OPTION'
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
ms.openlocfilehash: 1d651909e0f62f2db7478a6e0b37139d1f953196
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679136"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="b1b23-103">WAIT_OPTION 열거형</span><span class="sxs-lookup"><span data-stu-id="b1b23-103">WAIT_OPTION Enumeration</span></span>

<span data-ttu-id="b1b23-104">CLR (공용 언어 런타임) 블록에서 요청 된 작업을 수행할 때 호스트가 수행할 동작을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b23-104">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1b23-105">구문</span><span class="sxs-lookup"><span data-stu-id="b1b23-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="b1b23-106">구성원</span><span class="sxs-lookup"><span data-stu-id="b1b23-106">Members</span></span>  
  
|<span data-ttu-id="b1b23-107">멤버</span><span class="sxs-lookup"><span data-stu-id="b1b23-107">Member</span></span>|<span data-ttu-id="b1b23-108">설명</span><span class="sxs-lookup"><span data-stu-id="b1b23-108">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="b1b23-109">CLR이 [IHostTask:: Alert](ihosttask-alert-method.md) 메서드를 호출 하는 경우 작업을 활성화 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b1b23-109">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="b1b23-110">스레드가 차단 되는 경우 현재 OS 스레드에서 메시지를 펌프 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b1b23-110">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="b1b23-111">런타임은이 값을 스레드에서만 지정 합니다 <xref:System.Threading.ApartmentState.STA> .</span><span class="sxs-lookup"><span data-stu-id="b1b23-111">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="b1b23-112">호스트에서 지정 된 동기화 요청을 나눌 수 없음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b1b23-112">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="b1b23-113">즉, 호스트에서을 반환할 수 없습니다 `HOST_E_DEADLOCK` .</span><span class="sxs-lookup"><span data-stu-id="b1b23-113">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1b23-114">설명</span><span class="sxs-lookup"><span data-stu-id="b1b23-114">Remarks</span></span>  

 <span data-ttu-id="b1b23-115">[IHostTaskManager:: Sleep](ihosttaskmanager-sleep-method.md) 및 [IHostTaskManager:: switchtotask](ihosttaskmanager-switchtotask-method.md) 메서드는 모두이 형식의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b23-115">The [IHostTaskManager::Sleep](ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1b23-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1b23-116">Requirements</span></span>  

 <span data-ttu-id="b1b23-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1b23-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1b23-118">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b1b23-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b1b23-119">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b1b23-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1b23-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1b23-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b23-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1b23-121">See also</span></span>

- [<span data-ttu-id="b1b23-122">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="b1b23-122">Hosting Enumerations</span></span>](hosting-enumerations.md)
