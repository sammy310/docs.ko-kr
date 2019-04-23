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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67fd1a9174b04e42b53f2b866a1dfdd504362aa9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168391"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="c518c-102">ICorDebugArrayValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c518c-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="c518c-103">1 차원 또는 다차원 배열을 나타내는 ICorDebugHeapValue의 하위 클래스.</span><span class="sxs-lookup"><span data-stu-id="c518c-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c518c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c518c-104">Methods</span></span>  
  
|<span data-ttu-id="c518c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c518c-105">Method</span></span>|<span data-ttu-id="c518c-106">설명</span><span class="sxs-lookup"><span data-stu-id="c518c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c518c-107">GetBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="c518c-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="c518c-108">배열의 각 차원에 대 한 기본 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c518c-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="c518c-109">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="c518c-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="c518c-110">배열에 있는 요소의 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c518c-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="c518c-111">GetDimensions 메서드</span><span class="sxs-lookup"><span data-stu-id="c518c-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="c518c-112">배열의 차수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c518c-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="c518c-113">GetElement 메서드</span><span class="sxs-lookup"><span data-stu-id="c518c-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="c518c-114">배열의 지정된 된 요소를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c518c-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="c518c-115">GetElementAtPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="c518c-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="c518c-116">0부터 시작 하는 1 차원 배열로 간주 하 여 지정된 된 위치에서 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c518c-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="c518c-117">GetElementType 메서드</span><span class="sxs-lookup"><span data-stu-id="c518c-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="c518c-118">배열에서 간단한 형식의 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c518c-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="c518c-119">GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="c518c-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="c518c-120">배열의 차수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c518c-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="c518c-121">HasBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="c518c-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="c518c-122">배열의 기본 인덱스에 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c518c-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c518c-123">설명</span><span class="sxs-lookup"><span data-stu-id="c518c-123">Remarks</span></span>  
 <span data-ttu-id="c518c-124">`ICorDebugArrayValue` 1 차원 및 다차원 배열을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c518c-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c518c-125">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c518c-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c518c-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c518c-126">Requirements</span></span>  
 <span data-ttu-id="c518c-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c518c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c518c-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c518c-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c518c-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c518c-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c518c-130">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c518c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c518c-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="c518c-131">See also</span></span>

- [<span data-ttu-id="c518c-132">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c518c-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
