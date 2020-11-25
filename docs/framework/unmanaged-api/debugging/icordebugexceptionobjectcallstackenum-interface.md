---
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
ms.openlocfilehash: 1c45faecdb8b95af8d9e981962151c2c5d071a4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731893"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="b7756-102">ICorDebugExceptionObjectCallStackEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7756-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>

<span data-ttu-id="b7756-103">예외 개체에 포함된 호출 스택 정보에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b7756-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="b7756-104">이 인터페이스는 ICorDebugEnum 인터페이스의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b7756-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7756-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b7756-105">Methods</span></span>  
  
|<span data-ttu-id="b7756-106">메서드</span><span class="sxs-lookup"><span data-stu-id="b7756-106">Method</span></span>|<span data-ttu-id="b7756-107">설명</span><span class="sxs-lookup"><span data-stu-id="b7756-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7756-108">ICorDebugExceptionObjectCallStackEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="b7756-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="b7756-109">예외 개체의 호출 스택에 대 한 정보를 포함 하는 지정 된 수의 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7756-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7756-110">설명</span><span class="sxs-lookup"><span data-stu-id="b7756-110">Remarks</span></span>  

 <span data-ttu-id="b7756-111">`ICorDebugExceptionObjectCallStackEnum`인터페이스는 ICorDebugEnum 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7756-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="b7756-112">`ICorDebugExceptionObjectCallStackEnum` [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) 메서드를 호출 하 여 인스턴스가 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 개체로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="b7756-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="b7756-113">[ICorDebugExceptionObjectCallStackEnum:: Next](icordebugexceptionobjectcallstackenum-next-method.md) 메서드를 호출 하 여 컬렉션의 호출 스택 항목을 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7756-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7756-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7756-114">Requirements</span></span>  

 <span data-ttu-id="b7756-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7756-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7756-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7756-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7756-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7756-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7756-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7756-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7756-119">참조</span><span class="sxs-lookup"><span data-stu-id="b7756-119">See also</span></span>

- [<span data-ttu-id="b7756-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7756-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b7756-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="b7756-121">Debugging</span></span>](index.md)
