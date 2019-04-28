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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6575acfb1f75cbc8e3d59ddca5fea0953274cf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782956"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="bd1bb-102">ICorDebugReferenceValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd1bb-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="bd1bb-103">개체에 대 한 참조는 값을 관리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="bd1bb-104">(즉,이 메서드는 대 한 포인터를 관리 하는 합니다.) 이 인터페이스는 "ICorDebugValue"를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bd1bb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="bd1bb-105">Methods</span></span>  
  
|<span data-ttu-id="bd1bb-106">메서드</span><span class="sxs-lookup"><span data-stu-id="bd1bb-106">Method</span></span>|<span data-ttu-id="bd1bb-107">설명</span><span class="sxs-lookup"><span data-stu-id="bd1bb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bd1bb-108">Dereference 메서드</span><span class="sxs-lookup"><span data-stu-id="bd1bb-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="bd1bb-109">참조 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="bd1bb-110">DereferenceStrong 메서드</span><span class="sxs-lookup"><span data-stu-id="bd1bb-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="bd1bb-111">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-111">Not implemented.</span></span> <span data-ttu-id="bd1bb-112">이 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="bd1bb-113">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="bd1bb-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="bd1bb-114">참조 된 개체의 현재 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="bd1bb-115">IsNull 메서드</span><span class="sxs-lookup"><span data-stu-id="bd1bb-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="bd1bb-116">나타내는 값을 가져옵니다 여부를이 `ICorDebugReferenceValue` null 값인 경우,이 경우에 `ICorDebugReferenceValue` 개체를 가리키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="bd1bb-117">SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="bd1bb-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="bd1bb-118">현재 메모리 주소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-118">Sets the current memory address.</span></span> <span data-ttu-id="bd1bb-119">이 메서드가이 설정, `ICorDebugReferenceValue` 개체를 가리키도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd1bb-120">설명</span><span class="sxs-lookup"><span data-stu-id="bd1bb-120">Remarks</span></span>  
 <span data-ttu-id="bd1bb-121">디버깅된 된 프로세스는 계속 하는 경우는 CLR (공용 언어 런타임) 개체의 가비지 컬렉션을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="bd1bb-122">가비지 수집이 메모리에 개체를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="bd1bb-123">`ICorDebugReferenceValue` 됩니다 하나 보이도록 가비지 수집을 사용 하 여 가비지 컬렉션 후 해당 정보를 업데이트 하거나 가비지 컬렉션 전에 암시적으로 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="bd1bb-124">`ICorDebugReferenceValue` 디버깅된 된 프로세스 계속 된 후 개체가 암시적으로 무효화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="bd1bb-125">명시적으로 해제 되거나 표시 될 때까지 파생된 "ICorDebugHandleValue" 무효화 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd1bb-126">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd1bb-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd1bb-127">Requirements</span></span>  
 <span data-ttu-id="bd1bb-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bd1bb-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd1bb-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd1bb-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd1bb-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd1bb-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd1bb-131">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd1bb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd1bb-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="bd1bb-132">See also</span></span>

- [<span data-ttu-id="bd1bb-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd1bb-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
