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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fd42f13f699b0b79fd69311186f2b2ca0c9998a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149073"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="33171-102">ICorDebugBreakpointEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33171-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="33171-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugBreakpoint 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="33171-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33171-104">메서드</span><span class="sxs-lookup"><span data-stu-id="33171-104">Methods</span></span>  
  
|<span data-ttu-id="33171-105">메서드</span><span class="sxs-lookup"><span data-stu-id="33171-105">Method</span></span>|<span data-ttu-id="33171-106">설명</span><span class="sxs-lookup"><span data-stu-id="33171-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33171-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="33171-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="33171-108">지정 된 수를 가져옵니다 `ICorDebugBreakpoint` 인스턴스는 열거형에서 현재 위치에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="33171-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33171-109">설명</span><span class="sxs-lookup"><span data-stu-id="33171-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33171-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33171-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33171-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33171-111">Requirements</span></span>  
 <span data-ttu-id="33171-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="33171-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33171-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33171-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33171-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33171-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33171-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33171-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33171-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="33171-116">See also</span></span>

- [<span data-ttu-id="33171-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33171-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
