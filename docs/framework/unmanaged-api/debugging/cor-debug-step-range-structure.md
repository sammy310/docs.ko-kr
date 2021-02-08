---
description: '다음에 대 한 자세한 정보: COR_DEBUG_STEP_RANGE 구조체'
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
ms.openlocfilehash: 40462be4b165351b3265fa0833d19f18e0fa3a37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801841"
---
# <a name="cor_debug_step_range-structure"></a><span data-ttu-id="1d924-103">COR_DEBUG_STEP_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="1d924-103">COR_DEBUG_STEP_RANGE Structure</span></span>

<span data-ttu-id="1d924-104">코드 범위에 대한 오프셋 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1d924-104">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="1d924-105">이 구조는 [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) 메서드에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d924-105">This structure is used by the [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d924-106">구문</span><span class="sxs-lookup"><span data-stu-id="1d924-106">Syntax</span></span>  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="1d924-107">구성원</span><span class="sxs-lookup"><span data-stu-id="1d924-107">Members</span></span>  
  
|<span data-ttu-id="1d924-108">멤버</span><span class="sxs-lookup"><span data-stu-id="1d924-108">Member</span></span>|<span data-ttu-id="1d924-109">설명</span><span class="sxs-lookup"><span data-stu-id="1d924-109">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="1d924-110">범위의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="1d924-110">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="1d924-111">범위 끝의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="1d924-111">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d924-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d924-112">Requirements</span></span>  

 <span data-ttu-id="1d924-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d924-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d924-114">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="1d924-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="1d924-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d924-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d924-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d924-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d924-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d924-117">See also</span></span>

- [<span data-ttu-id="1d924-118">StepRange 메서드</span><span class="sxs-lookup"><span data-stu-id="1d924-118">StepRange Method</span></span>](icordebugstepper-steprange-method.md)
- [<span data-ttu-id="1d924-119">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="1d924-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="1d924-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="1d924-120">Debugging</span></span>](index.md)
