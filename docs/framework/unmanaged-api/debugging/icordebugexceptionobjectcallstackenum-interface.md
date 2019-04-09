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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7ed6c04a46a767ed122e54df0695429cf923b8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126206"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="26670-102">ICorDebugExceptionObjectCallStackEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26670-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="26670-103">예외 개체에 포함된 호출 스택 정보에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26670-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="26670-104">이 인터페이스는 ICorDebugEnum 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="26670-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26670-105">메서드</span><span class="sxs-lookup"><span data-stu-id="26670-105">Methods</span></span>  
  
|<span data-ttu-id="26670-106">메서드</span><span class="sxs-lookup"><span data-stu-id="26670-106">Method</span></span>|<span data-ttu-id="26670-107">설명</span><span class="sxs-lookup"><span data-stu-id="26670-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26670-108">ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="26670-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="26670-109">지정된 된 수를 가져옵니다 [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) 예외 개체의 호출 스택에 대 한 정보를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="26670-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26670-110">설명</span><span class="sxs-lookup"><span data-stu-id="26670-110">Remarks</span></span>  
 <span data-ttu-id="26670-111">`ICorDebugExceptionObjectCallStackEnum` ICorDebugEnum 인터페이스를 구현 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="26670-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="26670-112">`ICorDebugExceptionObjectCallStackEnum` 인스턴스 채워집니다 [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) 호출 하 여 개체를 [icordebugexceptionobjectvalue:: Enumerateexceptioncallstack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="26670-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="26670-113">호출 하 여 컬렉션의 호출 스택 항목을 열거할 수 있습니다 합니다 [icordebugexceptionobjectcallstackenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) 메서드</span><span class="sxs-lookup"><span data-stu-id="26670-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26670-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26670-114">Requirements</span></span>  
 <span data-ttu-id="26670-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="26670-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26670-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26670-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26670-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26670-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="26670-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="26670-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="26670-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="26670-119">See also</span></span>

- [<span data-ttu-id="26670-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26670-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="26670-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="26670-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
