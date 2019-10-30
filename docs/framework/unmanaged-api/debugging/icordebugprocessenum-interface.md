---
title: ICorDebugProcessEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum
helpviewer_keywords:
- ICorDebugProcessEnum interface [.NET Framework debugging]
ms.assetid: b63a507a-ca97-4be0-8e4f-401cce2125f6
topic_type:
- apiref
ms.openlocfilehash: 9f5406c35915e447831d233804413034a429e8a1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139781"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="933e6-102">ICorDebugProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="933e6-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="933e6-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugProcess 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="933e6-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="933e6-104">메서드</span><span class="sxs-lookup"><span data-stu-id="933e6-104">Methods</span></span>  
  
|<span data-ttu-id="933e6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="933e6-105">Method</span></span>|<span data-ttu-id="933e6-106">설명</span><span class="sxs-lookup"><span data-stu-id="933e6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="933e6-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="933e6-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-next-method.md)|<span data-ttu-id="933e6-108">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 `ICorDebugProcess` 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="933e6-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="933e6-109">주의</span><span class="sxs-lookup"><span data-stu-id="933e6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="933e6-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="933e6-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="933e6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="933e6-111">Requirements</span></span>  
 <span data-ttu-id="933e6-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="933e6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="933e6-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="933e6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="933e6-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="933e6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="933e6-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="933e6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="933e6-116">참조</span><span class="sxs-lookup"><span data-stu-id="933e6-116">See also</span></span>

- [<span data-ttu-id="933e6-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="933e6-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
