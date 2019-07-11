---
title: COR_DEBUG_STEP_RANGE 구조체
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bda8079cff8f5e8fafade03a02c3dfe8798c5ca
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740778"
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="33001-102">COR_DEBUG_STEP_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="33001-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="33001-103">코드 범위에 대한 오프셋 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="33001-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="33001-104">이 구조체를 사용 합니다 [icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="33001-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33001-105">구문</span><span class="sxs-lookup"><span data-stu-id="33001-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="33001-106">멤버</span><span class="sxs-lookup"><span data-stu-id="33001-106">Members</span></span>  
  
|<span data-ttu-id="33001-107">멤버</span><span class="sxs-lookup"><span data-stu-id="33001-107">Member</span></span>|<span data-ttu-id="33001-108">설명</span><span class="sxs-lookup"><span data-stu-id="33001-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="33001-109">범위의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="33001-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="33001-110">범위의 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="33001-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33001-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33001-111">Requirements</span></span>  
 <span data-ttu-id="33001-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="33001-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33001-113">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="33001-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="33001-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33001-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33001-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33001-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33001-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="33001-116">See also</span></span>

- [<span data-ttu-id="33001-117">StepRange 메서드</span><span class="sxs-lookup"><span data-stu-id="33001-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)
- [<span data-ttu-id="33001-118">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="33001-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="33001-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="33001-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
