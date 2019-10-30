---
title: ICorDebugCode4 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugCode4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4
helpviewer_keywords:
- ICorDebugCode4 interface [.NET Framework debugging]
ms.assetid: a3fdf523-274a-449c-920b-9fcb0aed1d97
topic_type:
- apiref
ms.openlocfilehash: 6c74a6c371ababb21bfda9b8dd2910d6a7881e6a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125536"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="5f831-102">ICorDebugCode4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f831-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="5f831-103">디버거가 함수의 지역 변수 및 인수를 열거할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f831-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f831-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5f831-104">Methods</span></span>  
  
|<span data-ttu-id="5f831-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5f831-105">Method</span></span>|<span data-ttu-id="5f831-106">설명</span><span class="sxs-lookup"><span data-stu-id="5f831-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f831-107">EnumerateVariableHomes 메서드</span><span class="sxs-lookup"><span data-stu-id="5f831-107">EnumerateVariableHomes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="5f831-108">함수의 지역 변수 및 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5f831-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f831-109">주의</span><span class="sxs-lookup"><span data-stu-id="5f831-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f831-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f831-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f831-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f831-111">Requirements</span></span>  
 <span data-ttu-id="5f831-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f831-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f831-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f831-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f831-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f831-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f831-115">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f831-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f831-116">참조</span><span class="sxs-lookup"><span data-stu-id="5f831-116">See also</span></span>

- [<span data-ttu-id="5f831-117">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f831-117">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="5f831-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f831-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
