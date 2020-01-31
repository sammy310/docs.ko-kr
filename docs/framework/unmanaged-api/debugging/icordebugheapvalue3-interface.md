---
title: ICorDebugHeapValue3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
ms.openlocfilehash: ddfe8cee8fdbca910ffa4f6989b1359ae5f7b11f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794377"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="fb74e-102">ICorDebugHeapValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb74e-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="fb74e-103">개체의 모니터 잠금 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="fb74e-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="fb74e-104">이 인터페이스는 ICorDebugHeapValue 및 ICorDebugHeapValue2 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb74e-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb74e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fb74e-105">Methods</span></span>  
  
|<span data-ttu-id="fb74e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="fb74e-106">Method</span></span>|<span data-ttu-id="fb74e-107">설명</span><span class="sxs-lookup"><span data-stu-id="fb74e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb74e-108">GetThreadOwningMonitorLock 메서드</span><span class="sxs-lookup"><span data-stu-id="fb74e-108">GetThreadOwningMonitorLock Method</span></span>](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="fb74e-109">이 개체에 대 한 모니터 잠금을 소유 하는 관리 되는 스레드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb74e-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="fb74e-110">GetMonitorEventWaitList 메서드</span><span class="sxs-lookup"><span data-stu-id="fb74e-110">GetMonitorEventWaitList Method</span></span>](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="fb74e-111">모니터 잠금과 연결 된 이벤트에서 큐에 대기 중인 스레드의 순서 있는 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb74e-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb74e-112">주의</span><span class="sxs-lookup"><span data-stu-id="fb74e-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb74e-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb74e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb74e-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb74e-114">Requirements</span></span>  
 <span data-ttu-id="fb74e-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb74e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb74e-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb74e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb74e-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb74e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb74e-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb74e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb74e-119">참조</span><span class="sxs-lookup"><span data-stu-id="fb74e-119">See also</span></span>

- [<span data-ttu-id="fb74e-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb74e-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fb74e-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="fb74e-121">Debugging</span></span>](index.md)
