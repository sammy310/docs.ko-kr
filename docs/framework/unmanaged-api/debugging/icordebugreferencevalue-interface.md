---
title: ICorDebugReferenceValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
ms.openlocfilehash: 2efba22b4ec372c5ddedd4982a29d66945d3511c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792124"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="d6e10-102">ICorDebugReferenceValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6e10-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="d6e10-103">개체에 대 한 참조 인 값을 관리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="d6e10-104">즉,이 인터페이스는 포인터를 관리 하는 메서드를 제공 합니다. 이 인터페이스는 "ICorDebugValue"를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6e10-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d6e10-105">Methods</span></span>  
  
|<span data-ttu-id="d6e10-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d6e10-106">Method</span></span>|<span data-ttu-id="d6e10-107">설명</span><span class="sxs-lookup"><span data-stu-id="d6e10-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6e10-108">Dereference 메서드</span><span class="sxs-lookup"><span data-stu-id="d6e10-108">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="d6e10-109">참조 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="d6e10-110">DereferenceStrong 메서드</span><span class="sxs-lookup"><span data-stu-id="d6e10-110">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="d6e10-111">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-111">Not implemented.</span></span> <span data-ttu-id="d6e10-112">이 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d6e10-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="d6e10-113">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="d6e10-113">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="d6e10-114">참조 된 개체의 현재 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="d6e10-115">IsNull 메서드</span><span class="sxs-lookup"><span data-stu-id="d6e10-115">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="d6e10-116">이 `ICorDebugReferenceValue`가 null 값 인지 여부를 나타내는 값을 가져옵니다 .이 경우 `ICorDebugReferenceValue`는 개체를 가리키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="d6e10-117">SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="d6e10-117">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="d6e10-118">현재 메모리 주소를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-118">Sets the current memory address.</span></span> <span data-ttu-id="d6e10-119">즉,이 메서드는 개체를 가리키도록이 `ICorDebugReferenceValue` 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6e10-120">주의</span><span class="sxs-lookup"><span data-stu-id="d6e10-120">Remarks</span></span>  
 <span data-ttu-id="d6e10-121">디버깅 된 프로세스가 계속 될 때 CLR (공용 언어 런타임)에서 개체에 대 한 가비지 수집을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="d6e10-122">가비지 컬렉션은 메모리에서 개체를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="d6e10-123">가비지 수집 후에는 해당 정보가 업데이트 되도록 `ICorDebugReferenceValue` 가비지 컬렉션과 상호 작용 하거나 가비지 수집 전에 암시적으로 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="d6e10-124">디버깅 된 프로세스가 계속 되 면 `ICorDebugReferenceValue` 개체가 암시적으로 무효화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="d6e10-125">파생 된 "ICorDebugHandleValue"은 명시적으로 해제 되거나 노출 될 때까지 무효화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6e10-126">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e10-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6e10-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6e10-127">Requirements</span></span>  
 <span data-ttu-id="d6e10-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e10-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6e10-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6e10-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6e10-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6e10-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6e10-131">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6e10-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e10-132">참조</span><span class="sxs-lookup"><span data-stu-id="d6e10-132">See also</span></span>

- [<span data-ttu-id="d6e10-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6e10-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
