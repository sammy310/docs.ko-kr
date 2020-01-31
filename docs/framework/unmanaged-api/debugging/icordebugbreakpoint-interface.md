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
ms.openlocfilehash: 53d8d219a13f2dade16a338efccf0837f8de0158
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784371"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="c2737-102">ICorDebugBreakpoint 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2737-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="c2737-103">함수의 중단점 또는 값에 대 한 조사식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2737-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2737-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c2737-104">Methods</span></span>  
  
|<span data-ttu-id="c2737-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c2737-105">Method</span></span>|<span data-ttu-id="c2737-106">설명</span><span class="sxs-lookup"><span data-stu-id="c2737-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2737-107">Activate 메서드</span><span class="sxs-lookup"><span data-stu-id="c2737-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="c2737-108">이 `ICorDebugBreakpoint`의 활성 상태를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2737-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="c2737-109">IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="c2737-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="c2737-110">이 `ICorDebugBreakpoint` 활성화 되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2737-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2737-111">주의</span><span class="sxs-lookup"><span data-stu-id="c2737-111">Remarks</span></span>  
 <span data-ttu-id="c2737-112">중단점은 조건식을 직접 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2737-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="c2737-113">이러한 기능이 필요한 경우 디버거는 `ICorDebugBreakpoint`위에서 해당 기능을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2737-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="c2737-114">ICorDebugFunctionBreakpoint 인터페이스는 함수 내에서 중단점을 지원 하기 위해 `ICorDebugBreakpoint`를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2737-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2737-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2737-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2737-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2737-116">Requirements</span></span>  
 <span data-ttu-id="c2737-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2737-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2737-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2737-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2737-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2737-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2737-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2737-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2737-121">참조</span><span class="sxs-lookup"><span data-stu-id="c2737-121">See also</span></span>

- [<span data-ttu-id="c2737-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2737-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
