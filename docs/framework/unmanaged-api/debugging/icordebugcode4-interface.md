---
description: '자세히 알아보기: ICorDebugCode4 인터페이스'
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
ms.openlocfilehash: 1276db5c55c3d98e5ffa379f6126f700d93c1670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764725"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="ae006-103">ICorDebugCode4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae006-103">ICorDebugCode4 Interface</span></span>

<span data-ttu-id="ae006-104">디버거가 함수의 지역 변수 및 인수를 열거할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae006-104">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae006-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ae006-105">Methods</span></span>  
  
|<span data-ttu-id="ae006-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ae006-106">Method</span></span>|<span data-ttu-id="ae006-107">설명</span><span class="sxs-lookup"><span data-stu-id="ae006-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae006-108">EnumerateVariableHomes 메서드</span><span class="sxs-lookup"><span data-stu-id="ae006-108">EnumerateVariableHomes Method</span></span>](icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="ae006-109">함수의 지역 변수 및 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae006-109">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae006-110">설명</span><span class="sxs-lookup"><span data-stu-id="ae006-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae006-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae006-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae006-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae006-112">Requirements</span></span>  

 <span data-ttu-id="ae006-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae006-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae006-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae006-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae006-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae006-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae006-116">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae006-116">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae006-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae006-117">See also</span></span>

- [<span data-ttu-id="ae006-118">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae006-118">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="ae006-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae006-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
