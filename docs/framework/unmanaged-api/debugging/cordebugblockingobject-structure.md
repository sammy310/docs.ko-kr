---
title: CorDebugBlockingObject 구조체
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12a114ea65aca544d653704cdfb01ed15d19c581
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609271"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="b7311-102">CorDebugBlockingObject 구조체</span><span class="sxs-lookup"><span data-stu-id="b7311-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="b7311-103">스레드가 차단 되는 특정 이유와 스레드를 차단 하는 개체를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7311-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7311-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7311-104">Syntax</span></span>  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="b7311-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b7311-105">Members</span></span>  
  
|<span data-ttu-id="b7311-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b7311-106">Member</span></span>|<span data-ttu-id="b7311-107">설명</span><span class="sxs-lookup"><span data-stu-id="b7311-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="b7311-108">스레드를 차단 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b7311-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="b7311-109">이 개체는 현재 동기화 된 상태의 기간에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7311-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="b7311-110">예상할 수 있는 경우 두 스레드가 동일한 동기화 된 상태 내에서 동일한 개체에서 차단 되는 [icordebugvalue:: Getaddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) 동일한 값을 반환 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b7311-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="b7311-111">그러나 인터페이스 수도 있고 해당 포인터 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7311-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="b7311-112">차단 작업 전에 시간을 밀리초 단위로 시간 초과 또는 무한 시간 초과 되지 않음을 나타내는 값을 됩니다. 시간 제한 값은 남아 있는 시간이 아닌 차단 작업에 대 한 총 기간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7311-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="b7311-113">이 개체에 스레드가 차단 되는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="b7311-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7311-114">설명</span><span class="sxs-lookup"><span data-stu-id="b7311-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7311-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7311-115">Requirements</span></span>  
 <span data-ttu-id="b7311-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7311-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7311-117">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="b7311-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="b7311-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7311-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7311-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7311-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7311-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7311-120">See also</span></span>

- [<span data-ttu-id="b7311-121">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="b7311-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="b7311-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="b7311-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
