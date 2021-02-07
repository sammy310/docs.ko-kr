---
description: '자세히 알아보기: ICorDebugReferenceValue 인터페이스'
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
ms.openlocfilehash: e516b1178b4f4268472dedd37d6443e673e16af6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690966"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="14e81-103">ICorDebugReferenceValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14e81-103">ICorDebugReferenceValue Interface</span></span>

<span data-ttu-id="14e81-104">개체에 대 한 참조 인 값을 관리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-104">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="14e81-105">즉,이 인터페이스는 포인터를 관리 하는 메서드를 제공 합니다. 이 인터페이스는 "ICorDebugValue"를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-105">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14e81-106">메서드</span><span class="sxs-lookup"><span data-stu-id="14e81-106">Methods</span></span>  
  
|<span data-ttu-id="14e81-107">메서드</span><span class="sxs-lookup"><span data-stu-id="14e81-107">Method</span></span>|<span data-ttu-id="14e81-108">설명</span><span class="sxs-lookup"><span data-stu-id="14e81-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14e81-109">Dereference 메서드</span><span class="sxs-lookup"><span data-stu-id="14e81-109">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="14e81-110">참조 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-110">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="14e81-111">DereferenceStrong 메서드</span><span class="sxs-lookup"><span data-stu-id="14e81-111">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="14e81-112">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-112">Not implemented.</span></span> <span data-ttu-id="14e81-113">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="14e81-113">Do not call this method.</span></span>|  
|[<span data-ttu-id="14e81-114">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="14e81-114">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="14e81-115">참조 된 개체의 현재 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-115">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="14e81-116">IsNull 메서드</span><span class="sxs-lookup"><span data-stu-id="14e81-116">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="14e81-117">가 null 값 인지 여부를 나타내는 값을 가져옵니다 .이 값이 이면이 `ICorDebugReferenceValue` `ICorDebugReferenceValue` 개체를 가리키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-117">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="14e81-118">SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="14e81-118">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="14e81-119">현재 메모리 주소를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-119">Sets the current memory address.</span></span> <span data-ttu-id="14e81-120">즉,이 메서드는 개체를 `ICorDebugReferenceValue` 가리키도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-120">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e81-121">설명</span><span class="sxs-lookup"><span data-stu-id="14e81-121">Remarks</span></span>  

 <span data-ttu-id="14e81-122">디버깅 된 프로세스가 계속 될 때 CLR (공용 언어 런타임)에서 개체에 대 한 가비지 수집을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-122">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="14e81-123">가비지 컬렉션은 메모리에서 개체를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-123">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="14e81-124">는 가비지 컬렉션과 `ICorDebugReferenceValue` 상호 작용 하 여 가비지 수집 후 정보를 업데이트 하거나 가비지 수집 전에 암시적으로 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-124">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="14e81-125">`ICorDebugReferenceValue`디버깅 된 프로세스가 계속 되 면 개체가 암시적으로 무효화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-125">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="14e81-126">파생 된 "ICorDebugHandleValue"은 명시적으로 해제 되거나 노출 될 때까지 무효화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-126">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14e81-127">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14e81-127">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14e81-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14e81-128">Requirements</span></span>  

 <span data-ttu-id="14e81-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14e81-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14e81-130">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14e81-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14e81-131">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14e81-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14e81-132">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14e81-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e81-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14e81-133">See also</span></span>

- [<span data-ttu-id="14e81-134">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14e81-134">Debugging Interfaces</span></span>](debugging-interfaces.md)
