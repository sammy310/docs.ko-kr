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
ms.openlocfilehash: 870ac1e62363493989fe638483ea474d648c8c69
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893313"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="1b3ee-102">ICorDebugCode4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b3ee-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="1b3ee-103">디버거가 함수의 지역 변수 및 인수를 열거할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ee-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b3ee-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1b3ee-104">Methods</span></span>  
  
|<span data-ttu-id="1b3ee-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1b3ee-105">Method</span></span>|<span data-ttu-id="1b3ee-106">설명</span><span class="sxs-lookup"><span data-stu-id="1b3ee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b3ee-107">EnumerateVariableHomes 메서드</span><span class="sxs-lookup"><span data-stu-id="1b3ee-107">EnumerateVariableHomes Method</span></span>](icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="1b3ee-108">함수의 지역 변수 및 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ee-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b3ee-109">설명</span><span class="sxs-lookup"><span data-stu-id="1b3ee-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b3ee-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ee-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b3ee-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b3ee-111">Requirements</span></span>  
 <span data-ttu-id="1b3ee-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b3ee-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b3ee-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b3ee-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b3ee-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b3ee-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b3ee-115">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b3ee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b3ee-116">참조</span><span class="sxs-lookup"><span data-stu-id="1b3ee-116">See also</span></span>

- [<span data-ttu-id="1b3ee-117">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b3ee-117">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="1b3ee-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b3ee-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
