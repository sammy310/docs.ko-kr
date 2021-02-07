---
description: '자세히 알아보기: CorDebugBlockingReason 열거형'
title: CorDebugBlockingReason 열거형
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
ms.openlocfilehash: c2d9c805549d046fe40ab5ea00f30e2fd0a680a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747109"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="674a5-103">CorDebugBlockingReason 열거형</span><span class="sxs-lookup"><span data-stu-id="674a5-103">CorDebugBlockingReason Enumeration</span></span>

<span data-ttu-id="674a5-104">지정된 개체에서 스레드가 차단될 수 있는 이유를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="674a5-104">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="674a5-105">구문</span><span class="sxs-lookup"><span data-stu-id="674a5-105">Syntax</span></span>  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="674a5-106">구성원</span><span class="sxs-lookup"><span data-stu-id="674a5-106">Members</span></span>  
  
|<span data-ttu-id="674a5-107">멤버</span><span class="sxs-lookup"><span data-stu-id="674a5-107">Member</span></span>|<span data-ttu-id="674a5-108">설명</span><span class="sxs-lookup"><span data-stu-id="674a5-108">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="674a5-109">내부 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="674a5-109">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="674a5-110">스레드에서 개체에 대 한 모니터 잠금과 연결 된 임계 영역을 가져오려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="674a5-110">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="674a5-111">일반적으로이는 또는 메서드 중 하나를 호출할 때 발생 <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="674a5-111">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="674a5-112">스레드가 개체에 대 한 모니터 잠금과 연결 된 이벤트를 기다리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674a5-112">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="674a5-113">일반적으로이는 메서드 중 하나를 호출할 때 발생 <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` 합니다.</span><span class="sxs-lookup"><span data-stu-id="674a5-113">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="674a5-114">설명</span><span class="sxs-lookup"><span data-stu-id="674a5-114">Remarks</span></span>  

 <span data-ttu-id="674a5-115">`BLOCKING_MONITOR_CRITICAL_SECTION`또는 `BLOCKING_MONITOR_EVENT` 멤버가 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조체에서 사용 되는 경우 `pBlockingObject` 구조체의 멤버는 입력 되는 개체를 나타내는 "ICorDebugValue" 인터페이스를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="674a5-115">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="674a5-116">[ICorDebugHeapValue3](icordebugheapvalue3-interface.md) 인터페이스를 구현 하는 것도 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="674a5-116">It is also guaranteed to implement the [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="674a5-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="674a5-117">Requirements</span></span>  

 <span data-ttu-id="674a5-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="674a5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="674a5-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="674a5-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="674a5-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="674a5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="674a5-121">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="674a5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="674a5-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="674a5-122">See also</span></span>

- [<span data-ttu-id="674a5-123">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="674a5-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="674a5-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="674a5-124">Debugging</span></span>](index.md)
