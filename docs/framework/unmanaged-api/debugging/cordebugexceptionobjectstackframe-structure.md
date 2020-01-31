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
ms.openlocfilehash: 2845c15d67e287d6efb0cd0a9c940b69de3a1c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789371"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="eda98-102">CorDebugExceptionObjectStackFrame 구조체</span><span class="sxs-lookup"><span data-stu-id="eda98-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="eda98-103">예외 개체의 스택 프레임 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eda98-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eda98-104">구문</span><span class="sxs-lookup"><span data-stu-id="eda98-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="eda98-105">Members</span><span class="sxs-lookup"><span data-stu-id="eda98-105">Members</span></span>  
  
|<span data-ttu-id="eda98-106">Member</span><span class="sxs-lookup"><span data-stu-id="eda98-106">Member</span></span>|<span data-ttu-id="eda98-107">설명</span><span class="sxs-lookup"><span data-stu-id="eda98-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="eda98-108">현재 프레임에 대 한 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eda98-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="eda98-109">현재 프레임에 대 한 명령 포인터 (EIP/RIP)의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="eda98-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="eda98-110">현재 프레임에 대 한 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="eda98-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="eda98-111">프레임이 외부 예외의 마지막 프레임 인지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="eda98-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eda98-112">주의</span><span class="sxs-lookup"><span data-stu-id="eda98-112">Remarks</span></span>  
 <span data-ttu-id="eda98-113">호출자는 더 이상 사용 되지 않는 경우 ICorDebugModule 개체에 대 한 포인터를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eda98-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eda98-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eda98-114">Requirements</span></span>  
 <span data-ttu-id="eda98-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eda98-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eda98-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eda98-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eda98-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eda98-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eda98-118">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eda98-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda98-119">참조</span><span class="sxs-lookup"><span data-stu-id="eda98-119">See also</span></span>

- [<span data-ttu-id="eda98-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="eda98-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="eda98-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="eda98-121">Debugging</span></span>](index.md)
