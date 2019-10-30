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
ms.openlocfilehash: 206e4fb232f4786a76525d24aa379b25d6d2f71d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099353"
---
# <a name="cor_debug_step_range-structure"></a><span data-ttu-id="d4cc0-102">COR_DEBUG_STEP_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="d4cc0-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="d4cc0-103">코드 범위에 대한 오프셋 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d4cc0-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="d4cc0-104">이 구조는 [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) 메서드에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4cc0-104">This structure is used by the [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4cc0-105">구문</span><span class="sxs-lookup"><span data-stu-id="d4cc0-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="d4cc0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d4cc0-106">Members</span></span>  
  
|<span data-ttu-id="d4cc0-107">멤버</span><span class="sxs-lookup"><span data-stu-id="d4cc0-107">Member</span></span>|<span data-ttu-id="d4cc0-108">설명</span><span class="sxs-lookup"><span data-stu-id="d4cc0-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="d4cc0-109">범위의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="d4cc0-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="d4cc0-110">범위 끝의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="d4cc0-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4cc0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4cc0-111">Requirements</span></span>  
 <span data-ttu-id="d4cc0-112">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4cc0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4cc0-113">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="d4cc0-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="d4cc0-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4cc0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4cc0-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4cc0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4cc0-116">참조</span><span class="sxs-lookup"><span data-stu-id="d4cc0-116">See also</span></span>

- [<span data-ttu-id="d4cc0-117">StepRange 메서드</span><span class="sxs-lookup"><span data-stu-id="d4cc0-117">StepRange Method</span></span>](icordebugstepper-steprange-method.md)
- [<span data-ttu-id="d4cc0-118">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="d4cc0-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="d4cc0-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="d4cc0-119">Debugging</span></span>](index.md)
