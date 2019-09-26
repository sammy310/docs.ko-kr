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
ms.openlocfilehash: 57de11c1c40c05befcf3c99c31c2e07e1ecaec5a
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71273966"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="1884b-102">CorDebugBlockingObject 구조체</span><span class="sxs-lookup"><span data-stu-id="1884b-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="1884b-103">스레드를 차단 하는 개체와 스레드가 차단 되는 특정 이유를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1884b-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1884b-104">구문</span><span class="sxs-lookup"><span data-stu-id="1884b-104">Syntax</span></span>  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="1884b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1884b-105">Members</span></span>  
  
|<span data-ttu-id="1884b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1884b-106">Member</span></span>|<span data-ttu-id="1884b-107">설명</span><span class="sxs-lookup"><span data-stu-id="1884b-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="1884b-108">스레드가 차단 하 고 있는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1884b-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="1884b-109">이 개체는 현재 동기화 된 상태의 기간 동안만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="1884b-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="1884b-110">동일 하 게 동기화 된 상태에서 두 스레드가 동일한 개체에서 차단 하는 경우에는 [ICorDebugValue:: GetAddress](icordebugvalue-getaddress-method.md) 메서드가 같은 값을 반환할 것으로 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1884b-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="1884b-111">그러나 인터페이스는 포인터가 될 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1884b-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="1884b-112">차단 작업의 제한 시간이 초과 될 때까지 걸리는 시간 (밀리초) 이거나, 제한 시간이 초과 되지 않음을 나타내는 무한 값입니다. 제한 시간 값은 계속 남아 있는 시간을 제외 하 고 차단 작업의 총 시간 길이를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1884b-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="1884b-113">이 개체에서 스레드가 차단 된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="1884b-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1884b-114">설명</span><span class="sxs-lookup"><span data-stu-id="1884b-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1884b-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1884b-115">Requirements</span></span>  
 <span data-ttu-id="1884b-116">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1884b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1884b-117">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="1884b-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="1884b-118">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1884b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1884b-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1884b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1884b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1884b-120">See also</span></span>

- [<span data-ttu-id="1884b-121">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="1884b-121">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="1884b-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="1884b-122">Debugging</span></span>](index.md)
