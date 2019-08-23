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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ec40de7fe9e12315987e65e48f1727f5d5b80ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960725"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="39de9-102">ICorDebugCode4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39de9-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="39de9-103">디버거가 함수의 지역 변수 및 인수를 열거할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39de9-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39de9-104">메서드</span><span class="sxs-lookup"><span data-stu-id="39de9-104">Methods</span></span>  
  
|<span data-ttu-id="39de9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="39de9-105">Method</span></span>|<span data-ttu-id="39de9-106">설명</span><span class="sxs-lookup"><span data-stu-id="39de9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39de9-107">EnumerateVariableHomes 메서드</span><span class="sxs-lookup"><span data-stu-id="39de9-107">EnumerateVariableHomes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="39de9-108">함수의 지역 변수 및 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="39de9-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39de9-109">설명</span><span class="sxs-lookup"><span data-stu-id="39de9-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39de9-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39de9-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39de9-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39de9-111">Requirements</span></span>  
 <span data-ttu-id="39de9-112">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="39de9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39de9-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39de9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39de9-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39de9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39de9-115">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39de9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39de9-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="39de9-116">See also</span></span>

- [<span data-ttu-id="39de9-117">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39de9-117">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="39de9-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39de9-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
