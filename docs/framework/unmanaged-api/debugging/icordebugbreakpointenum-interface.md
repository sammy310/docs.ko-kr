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
ms.openlocfilehash: 5fb4a8a508cde4455bbee8c08432d3549e3fac43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122751"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="50e2c-102">ICorDebugBreakpointEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="50e2c-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="50e2c-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugBreakpoint 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="50e2c-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50e2c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="50e2c-104">Methods</span></span>  
  
|<span data-ttu-id="50e2c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="50e2c-105">Method</span></span>|<span data-ttu-id="50e2c-106">설명</span><span class="sxs-lookup"><span data-stu-id="50e2c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50e2c-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="50e2c-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="50e2c-108">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 `ICorDebugBreakpoint` 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="50e2c-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50e2c-109">주의</span><span class="sxs-lookup"><span data-stu-id="50e2c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50e2c-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50e2c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50e2c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="50e2c-111">Requirements</span></span>  
 <span data-ttu-id="50e2c-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50e2c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50e2c-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50e2c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50e2c-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50e2c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50e2c-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50e2c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e2c-116">참조</span><span class="sxs-lookup"><span data-stu-id="50e2c-116">See also</span></span>

- [<span data-ttu-id="50e2c-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="50e2c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
