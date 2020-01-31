---
title: ICorDebugArrayValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
ms.openlocfilehash: 0944f3379c18cba56ab65fe40a5b94a64d8a8991
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778198"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="e0ab4-102">ICorDebugArrayValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0ab4-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="e0ab4-103">일차원 또는 다차원 배열을 나타내는 ICorDebugHeapValue의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0ab4-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e0ab4-104">Methods</span></span>  
  
|<span data-ttu-id="e0ab4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e0ab4-105">Method</span></span>|<span data-ttu-id="e0ab4-106">설명</span><span class="sxs-lookup"><span data-stu-id="e0ab4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0ab4-107">GetBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="e0ab4-107">GetBaseIndicies Method</span></span>](icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="e0ab4-108">배열에 있는 각 차원의 기본 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="e0ab4-109">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="e0ab4-109">GetCount Method</span></span>](icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="e0ab4-110">배열에 있는 요소의 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="e0ab4-111">GetDimensions 메서드</span><span class="sxs-lookup"><span data-stu-id="e0ab4-111">GetDimensions Method</span></span>](icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="e0ab4-112">배열의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="e0ab4-113">GetElement 메서드</span><span class="sxs-lookup"><span data-stu-id="e0ab4-113">GetElement Method</span></span>](icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="e0ab4-114">배열에서 지정 된 요소를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="e0ab4-115">GetElementAtPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="e0ab4-115">GetElementAtPosition Method</span></span>](icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="e0ab4-116">배열을 0부터 시작 하는 1 차원 배열로 처리 하는 지정 된 위치에 있는 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="e0ab4-117">GetElementType 메서드</span><span class="sxs-lookup"><span data-stu-id="e0ab4-117">GetElementType Method</span></span>](icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="e0ab4-118">배열에 있는 요소의 단순 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="e0ab4-119">GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="e0ab4-119">GetRank Method</span></span>](icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="e0ab4-120">배열의 차수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="e0ab4-121">HasBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="e0ab4-121">HasBaseIndicies Method</span></span>](icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="e0ab4-122">배열에 기본 인덱스가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0ab4-123">주의</span><span class="sxs-lookup"><span data-stu-id="e0ab4-123">Remarks</span></span>  
 <span data-ttu-id="e0ab4-124">`ICorDebugArrayValue`는 1 차원 배열 및 다차원 배열을 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0ab4-125">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0ab4-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0ab4-126">Requirements</span></span>  
 <span data-ttu-id="e0ab4-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0ab4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0ab4-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0ab4-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0ab4-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0ab4-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0ab4-130">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0ab4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ab4-131">참조</span><span class="sxs-lookup"><span data-stu-id="e0ab4-131">See also</span></span>

- [<span data-ttu-id="e0ab4-132">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0ab4-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
