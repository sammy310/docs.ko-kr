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
ms.openlocfilehash: 056d41df328de5796eec9f04589205d18b408f1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732803"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="f02ca-102">WAIT_OPTION 열거형</span><span class="sxs-lookup"><span data-stu-id="f02ca-102">WAIT_OPTION Enumeration</span></span>

<span data-ttu-id="f02ca-103">CLR (공용 언어 런타임) 블록에서 요청 된 작업을 수행할 때 호스트가 수행할 동작을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f02ca-104">구문</span><span class="sxs-lookup"><span data-stu-id="f02ca-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="f02ca-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f02ca-105">Members</span></span>  
  
|<span data-ttu-id="f02ca-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f02ca-106">Member</span></span>|<span data-ttu-id="f02ca-107">설명</span><span class="sxs-lookup"><span data-stu-id="f02ca-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="f02ca-108">CLR이 [IHostTask:: Alert](ihosttask-alert-method.md) 메서드를 호출 하는 경우 작업을 활성화 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="f02ca-109">스레드가 차단 되는 경우 현재 OS 스레드에서 메시지를 펌프 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="f02ca-110">런타임은이 값을 스레드에서만 지정 합니다 <xref:System.Threading.ApartmentState.STA> .</span><span class="sxs-lookup"><span data-stu-id="f02ca-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="f02ca-111">호스트에서 지정 된 동기화 요청을 나눌 수 없음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="f02ca-112">즉, 호스트에서을 반환할 수 없습니다 `HOST_E_DEADLOCK` .</span><span class="sxs-lookup"><span data-stu-id="f02ca-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f02ca-113">설명</span><span class="sxs-lookup"><span data-stu-id="f02ca-113">Remarks</span></span>  

 <span data-ttu-id="f02ca-114">[IHostTaskManager:: Sleep](ihosttaskmanager-sleep-method.md) 및 [IHostTaskManager:: switchtotask](ihosttaskmanager-switchtotask-method.md) 메서드는 모두이 형식의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-114">The [IHostTaskManager::Sleep](ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f02ca-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f02ca-115">Requirements</span></span>  

 <span data-ttu-id="f02ca-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f02ca-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f02ca-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f02ca-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f02ca-118">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f02ca-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f02ca-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f02ca-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02ca-120">참조</span><span class="sxs-lookup"><span data-stu-id="f02ca-120">See also</span></span>

- [<span data-ttu-id="f02ca-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="f02ca-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
