---
description: '자세히 알아보기: ICorDebugExceptionObjectCallStackEnum 인터페이스'
title: ICorDebugExceptionObjectCallStackEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: c72f4299bf3ebc5de2d2ed196801d93ff5fe4356
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693358"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="c5455-103">ICorDebugExceptionObjectCallStackEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5455-103">ICorDebugExceptionObjectCallStackEnum Interface</span></span>

<span data-ttu-id="c5455-104">예외 개체에 포함된 호출 스택 정보에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5455-104">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="c5455-105">이 인터페이스는 ICorDebugEnum 인터페이스의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c5455-105">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5455-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c5455-106">Methods</span></span>  
  
|<span data-ttu-id="c5455-107">메서드</span><span class="sxs-lookup"><span data-stu-id="c5455-107">Method</span></span>|<span data-ttu-id="c5455-108">설명</span><span class="sxs-lookup"><span data-stu-id="c5455-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5455-109">ICorDebugExceptionObjectCallStackEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="c5455-109">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="c5455-110">예외 개체의 호출 스택에 대 한 정보를 포함 하는 지정 된 수의 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c5455-110">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5455-111">설명</span><span class="sxs-lookup"><span data-stu-id="c5455-111">Remarks</span></span>  

 <span data-ttu-id="c5455-112">`ICorDebugExceptionObjectCallStackEnum`인터페이스는 ICorDebugEnum 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5455-112">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="c5455-113">`ICorDebugExceptionObjectCallStackEnum` [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) 메서드를 호출 하 여 인스턴스가 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 개체로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="c5455-113">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="c5455-114">[ICorDebugExceptionObjectCallStackEnum:: Next](icordebugexceptionobjectcallstackenum-next-method.md) 메서드를 호출 하 여 컬렉션의 호출 스택 항목을 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5455-114">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5455-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5455-115">Requirements</span></span>  

 <span data-ttu-id="c5455-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5455-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5455-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5455-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5455-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5455-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5455-119">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5455-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5455-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5455-120">See also</span></span>

- [<span data-ttu-id="c5455-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5455-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c5455-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="c5455-122">Debugging</span></span>](index.md)
