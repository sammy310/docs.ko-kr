---
title: ICorDebugHandleValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
ms.openlocfilehash: 406468fc6e2b68e8c8e1dfbd0f0f18cce3f013ab
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794453"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="154ca-102">ICorDebugHandleValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="154ca-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="154ca-103">디버거에서 가비지 수집에 대 한 핸들을 만든 참조 값을 나타내는 ICorDebugReferenceValue의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="154ca-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="154ca-104">메서드</span><span class="sxs-lookup"><span data-stu-id="154ca-104">Methods</span></span>  
  
|<span data-ttu-id="154ca-105">메서드</span><span class="sxs-lookup"><span data-stu-id="154ca-105">Method</span></span>|<span data-ttu-id="154ca-106">설명</span><span class="sxs-lookup"><span data-stu-id="154ca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="154ca-107">Dispose 메서드</span><span class="sxs-lookup"><span data-stu-id="154ca-107">Dispose Method</span></span>](icordebughandlevalue-dispose-method.md)|<span data-ttu-id="154ca-108">인터페이스 포인터를 명시적으로 해제 하지 않고이 `ICorDebugHandleValue` 개체에서 참조 하는 핸들을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="154ca-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="154ca-109">GetHandleType 메서드</span><span class="sxs-lookup"><span data-stu-id="154ca-109">GetHandleType Method</span></span>](icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="154ca-110">이 `ICorDebugHandleValue`에서 참조 하는 핸들의 종류를 설명 하는 CorDebugHandleType 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="154ca-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="154ca-111">주의</span><span class="sxs-lookup"><span data-stu-id="154ca-111">Remarks</span></span>  
 <span data-ttu-id="154ca-112">디버깅 된 코드의 실행이 중단 되 면 `ICorDebugReferenceValue` 개체가 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="154ca-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="154ca-113">`ICorDebugHandleValue`은 명시적으로 해제 될 때까지 중단 및 연속을 통해 참조를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="154ca-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="154ca-114">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="154ca-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="154ca-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="154ca-115">Requirements</span></span>  
 <span data-ttu-id="154ca-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="154ca-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="154ca-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="154ca-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="154ca-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="154ca-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="154ca-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="154ca-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154ca-120">참조</span><span class="sxs-lookup"><span data-stu-id="154ca-120">See also</span></span>

- [<span data-ttu-id="154ca-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="154ca-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
