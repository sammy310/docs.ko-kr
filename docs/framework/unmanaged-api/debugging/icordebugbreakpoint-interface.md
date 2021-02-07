---
description: '자세히 알아보기: ICorDebugBreakpoint 인터페이스'
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
ms.openlocfilehash: 63917512cceeccedea37acdf2ba7ab3b849d9fad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711806"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="7da9b-103">ICorDebugBreakpoint 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7da9b-103">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="7da9b-104">함수의 중단점 또는 값에 대 한 조사식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7da9b-104">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7da9b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7da9b-105">Methods</span></span>  
  
|<span data-ttu-id="7da9b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="7da9b-106">Method</span></span>|<span data-ttu-id="7da9b-107">설명</span><span class="sxs-lookup"><span data-stu-id="7da9b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7da9b-108">Activate 메서드</span><span class="sxs-lookup"><span data-stu-id="7da9b-108">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="7da9b-109">이의 활성 상태를 설정 합니다 `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="7da9b-109">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="7da9b-110">IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="7da9b-110">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="7da9b-111">이가 활성 상태 인지 여부를 나타내는 값을 가져옵니다 `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="7da9b-111">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7da9b-112">설명</span><span class="sxs-lookup"><span data-stu-id="7da9b-112">Remarks</span></span>  

 <span data-ttu-id="7da9b-113">중단점은 조건식을 직접 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7da9b-113">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="7da9b-114">이러한 기능이 필요한 경우 디버거는 위에서이 기능을 구현 해야 합니다 `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="7da9b-114">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="7da9b-115">ICorDebugFunctionBreakpoint 인터페이스는 `ICorDebugBreakpoint` 함수 내에서 중단점을 지원 하도록 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7da9b-115">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7da9b-116">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7da9b-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7da9b-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7da9b-117">Requirements</span></span>  

 <span data-ttu-id="7da9b-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7da9b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7da9b-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7da9b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7da9b-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7da9b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7da9b-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7da9b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da9b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7da9b-122">See also</span></span>

- [<span data-ttu-id="7da9b-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7da9b-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
