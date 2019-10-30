---
title: ICorDebugBreakpoint 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: 29bb84341c2cb4177c43f798d25a1a6d50099aa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122792"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="d1b16-102">ICorDebugBreakpoint 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1b16-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="d1b16-103">함수의 중단점 또는 값에 대 한 조사식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1b16-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1b16-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d1b16-104">Methods</span></span>  
  
|<span data-ttu-id="d1b16-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d1b16-105">Method</span></span>|<span data-ttu-id="d1b16-106">설명</span><span class="sxs-lookup"><span data-stu-id="d1b16-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1b16-107">Activate 메서드</span><span class="sxs-lookup"><span data-stu-id="d1b16-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="d1b16-108">이 `ICorDebugBreakpoint`의 활성 상태를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b16-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="d1b16-109">IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="d1b16-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="d1b16-110">이 `ICorDebugBreakpoint` 활성화 되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d1b16-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1b16-111">주의</span><span class="sxs-lookup"><span data-stu-id="d1b16-111">Remarks</span></span>  
 <span data-ttu-id="d1b16-112">중단점은 조건식을 직접 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b16-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="d1b16-113">이러한 기능이 필요한 경우 디버거는 `ICorDebugBreakpoint`위에서 해당 기능을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b16-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="d1b16-114">ICorDebugFunctionBreakpoint 인터페이스는 함수 내에서 중단점을 지원 하기 위해 `ICorDebugBreakpoint`를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b16-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1b16-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b16-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1b16-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1b16-116">Requirements</span></span>  
 <span data-ttu-id="d1b16-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1b16-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1b16-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1b16-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1b16-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1b16-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1b16-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1b16-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b16-121">참조</span><span class="sxs-lookup"><span data-stu-id="d1b16-121">See also</span></span>

- [<span data-ttu-id="d1b16-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1b16-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
