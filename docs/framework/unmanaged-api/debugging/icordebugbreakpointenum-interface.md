---
title: ICorDebugBreakpointEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
ms.openlocfilehash: e391a02571481d75ce88ae3f3b2b6421705d661c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894711"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="3d108-102">ICorDebugBreakpointEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d108-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="3d108-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugBreakpoint 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d108-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d108-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3d108-104">Methods</span></span>  
  
|<span data-ttu-id="3d108-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3d108-105">Method</span></span>|<span data-ttu-id="3d108-106">설명</span><span class="sxs-lookup"><span data-stu-id="3d108-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d108-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="3d108-107">Next Method</span></span>](icordebugbreakpointenum-next-method.md)|<span data-ttu-id="3d108-108">현재 위치에서 시작 하 `ICorDebugBreakpoint` 여 열거형에서 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d108-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d108-109">설명</span><span class="sxs-lookup"><span data-stu-id="3d108-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d108-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d108-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d108-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d108-111">Requirements</span></span>  
 <span data-ttu-id="3d108-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d108-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d108-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d108-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d108-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d108-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d108-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d108-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d108-116">참조</span><span class="sxs-lookup"><span data-stu-id="3d108-116">See also</span></span>

- [<span data-ttu-id="3d108-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d108-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
