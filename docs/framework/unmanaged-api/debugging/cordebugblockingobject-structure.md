---
description: '자세히 알아보기: CorDebugBlockingObject Structure'
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
ms.openlocfilehash: 2b16af5eecb01067c2ee6811613f964af391f345
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712222"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="a2ca6-103">CorDebugBlockingObject 구조체</span><span class="sxs-lookup"><span data-stu-id="a2ca6-103">CorDebugBlockingObject Structure</span></span>

<span data-ttu-id="a2ca6-104">스레드를 차단 하는 개체와 스레드가 차단 되는 특정 이유를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ca6-104">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2ca6-105">구문</span><span class="sxs-lookup"><span data-stu-id="a2ca6-105">Syntax</span></span>  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="a2ca6-106">구성원</span><span class="sxs-lookup"><span data-stu-id="a2ca6-106">Members</span></span>  
  
|<span data-ttu-id="a2ca6-107">멤버</span><span class="sxs-lookup"><span data-stu-id="a2ca6-107">Member</span></span>|<span data-ttu-id="a2ca6-108">설명</span><span class="sxs-lookup"><span data-stu-id="a2ca6-108">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="a2ca6-109">스레드가 차단 하 고 있는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ca6-109">The object on which the thread is blocking.</span></span> <span data-ttu-id="a2ca6-110">이 개체는 현재 동기화 된 상태의 기간 동안만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ca6-110">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="a2ca6-111">동일 하 게 동기화 된 상태에서 두 스레드가 동일한 개체에서 차단 하는 경우에는 [ICorDebugValue:: GetAddress](icordebugvalue-getaddress-method.md) 메서드가 같은 값을 반환할 것으로 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ca6-111">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="a2ca6-112">그러나 인터페이스는 포인터가 될 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ca6-112">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="a2ca6-113">차단 작업의 제한 시간이 초과 될 때까지 걸리는 시간 (밀리초) 이거나, 제한 시간이 초과 되지 않음을 나타내는 무한 값입니다. 제한 시간 값은 계속 남아 있는 시간을 제외 하 고 차단 작업의 총 시간 길이를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ca6-113">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="a2ca6-114">이 개체에서 스레드가 차단 된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ca6-114">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2ca6-115">설명</span><span class="sxs-lookup"><span data-stu-id="a2ca6-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2ca6-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2ca6-116">Requirements</span></span>  

 <span data-ttu-id="a2ca6-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2ca6-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2ca6-118">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="a2ca6-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="a2ca6-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2ca6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2ca6-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2ca6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ca6-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2ca6-121">See also</span></span>

- [<span data-ttu-id="a2ca6-122">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="a2ca6-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="a2ca6-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="a2ca6-123">Debugging</span></span>](index.md)
