---
title: CorDebugExceptionObjectStackFrame 구조체
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
ms.openlocfilehash: 7eccaf984b187e463195bb3804f87bbb2c7ad47b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795926"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="a74c4-102">CorDebugExceptionObjectStackFrame 구조체</span><span class="sxs-lookup"><span data-stu-id="a74c4-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="a74c4-103">예외 개체의 스택 프레임 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a74c4-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a74c4-104">구문</span><span class="sxs-lookup"><span data-stu-id="a74c4-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="a74c4-105">구성원</span><span class="sxs-lookup"><span data-stu-id="a74c4-105">Members</span></span>  
  
|<span data-ttu-id="a74c4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a74c4-106">Member</span></span>|<span data-ttu-id="a74c4-107">설명</span><span class="sxs-lookup"><span data-stu-id="a74c4-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="a74c4-108">현재 프레임에 대 한 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a74c4-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="a74c4-109">현재 프레임에 대 한 명령 포인터 (EIP/RIP)의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a74c4-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="a74c4-110">현재 프레임에 대 한 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a74c4-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="a74c4-111">프레임이 외부 예외의 마지막 프레임 인지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a74c4-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a74c4-112">설명</span><span class="sxs-lookup"><span data-stu-id="a74c4-112">Remarks</span></span>  
 <span data-ttu-id="a74c4-113">호출자는 더 이상 사용 되지 않는 경우 ICorDebugModule 개체에 대 한 포인터를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a74c4-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a74c4-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a74c4-114">Requirements</span></span>  
 <span data-ttu-id="a74c4-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a74c4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a74c4-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a74c4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a74c4-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a74c4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a74c4-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a74c4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a74c4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a74c4-119">See also</span></span>

- [<span data-ttu-id="a74c4-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="a74c4-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="a74c4-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="a74c4-121">Debugging</span></span>](index.md)
