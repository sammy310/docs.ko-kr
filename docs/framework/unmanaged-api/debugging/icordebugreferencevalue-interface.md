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
ms.openlocfilehash: 6c6ff428e378e973d8846674ffacdcd04b2dbdbc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378341"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="00f4f-102">ICorDebugReferenceValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00f4f-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="00f4f-103">개체에 대 한 참조 인 값을 관리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="00f4f-104">즉,이 인터페이스는 포인터를 관리 하는 메서드를 제공 합니다. 이 인터페이스는 "ICorDebugValue"를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00f4f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="00f4f-105">Methods</span></span>  
  
|<span data-ttu-id="00f4f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="00f4f-106">Method</span></span>|<span data-ttu-id="00f4f-107">설명</span><span class="sxs-lookup"><span data-stu-id="00f4f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00f4f-108">Dereference 메서드</span><span class="sxs-lookup"><span data-stu-id="00f4f-108">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="00f4f-109">참조 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="00f4f-110">DereferenceStrong 메서드</span><span class="sxs-lookup"><span data-stu-id="00f4f-110">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="00f4f-111">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-111">Not implemented.</span></span> <span data-ttu-id="00f4f-112">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="00f4f-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="00f4f-113">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="00f4f-113">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="00f4f-114">참조 된 개체의 현재 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="00f4f-115">IsNull 메서드</span><span class="sxs-lookup"><span data-stu-id="00f4f-115">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="00f4f-116">가 null 값 인지 여부를 나타내는 값을 가져옵니다 .이 값이 이면이 `ICorDebugReferenceValue` `ICorDebugReferenceValue` 개체를 가리키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="00f4f-117">SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="00f4f-117">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="00f4f-118">현재 메모리 주소를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-118">Sets the current memory address.</span></span> <span data-ttu-id="00f4f-119">즉,이 메서드는 개체를 `ICorDebugReferenceValue` 가리키도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00f4f-120">설명</span><span class="sxs-lookup"><span data-stu-id="00f4f-120">Remarks</span></span>  
 <span data-ttu-id="00f4f-121">디버깅 된 프로세스가 계속 될 때 CLR (공용 언어 런타임)에서 개체에 대 한 가비지 수집을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="00f4f-122">가비지 컬렉션은 메모리에서 개체를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="00f4f-123">는 가비지 컬렉션과 `ICorDebugReferenceValue` 상호 작용 하 여 가비지 수집 후 정보를 업데이트 하거나 가비지 수집 전에 암시적으로 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="00f4f-124">`ICorDebugReferenceValue`디버깅 된 프로세스가 계속 되 면 개체가 암시적으로 무효화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="00f4f-125">파생 된 "ICorDebugHandleValue"은 명시적으로 해제 되거나 노출 될 때까지 무효화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00f4f-126">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00f4f-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00f4f-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00f4f-127">Requirements</span></span>  
 <span data-ttu-id="00f4f-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00f4f-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00f4f-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00f4f-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00f4f-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00f4f-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00f4f-131">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00f4f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00f4f-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00f4f-132">See also</span></span>

- [<span data-ttu-id="00f4f-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00f4f-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
