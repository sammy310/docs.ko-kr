---
description: '자세히 알아보기: ICorDebugArrayValue 인터페이스'
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
ms.openlocfilehash: 2b91c910b9444b061b4a6bea715667bca6a4629c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722895"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="8f0c9-103">ICorDebugArrayValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f0c9-103">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="8f0c9-104">일차원 또는 다차원 배열을 나타내는 ICorDebugHeapValue의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-104">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f0c9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8f0c9-105">Methods</span></span>  
  
|<span data-ttu-id="8f0c9-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8f0c9-106">Method</span></span>|<span data-ttu-id="8f0c9-107">설명</span><span class="sxs-lookup"><span data-stu-id="8f0c9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f0c9-108">GetBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="8f0c9-108">GetBaseIndicies Method</span></span>](icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="8f0c9-109">배열에 있는 각 차원의 기본 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-109">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="8f0c9-110">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="8f0c9-110">GetCount Method</span></span>](icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="8f0c9-111">배열에 있는 요소의 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-111">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="8f0c9-112">GetDimensions 메서드</span><span class="sxs-lookup"><span data-stu-id="8f0c9-112">GetDimensions Method</span></span>](icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="8f0c9-113">배열의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-113">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="8f0c9-114">GetElement 메서드</span><span class="sxs-lookup"><span data-stu-id="8f0c9-114">GetElement Method</span></span>](icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="8f0c9-115">배열에서 지정 된 요소를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-115">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="8f0c9-116">GetElementAtPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="8f0c9-116">GetElementAtPosition Method</span></span>](icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="8f0c9-117">배열을 0부터 시작 하는 1 차원 배열로 처리 하는 지정 된 위치에 있는 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-117">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="8f0c9-118">GetElementType 메서드</span><span class="sxs-lookup"><span data-stu-id="8f0c9-118">GetElementType Method</span></span>](icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="8f0c9-119">배열에 있는 요소의 단순 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-119">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="8f0c9-120">GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="8f0c9-120">GetRank Method</span></span>](icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="8f0c9-121">배열의 차수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-121">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="8f0c9-122">HasBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="8f0c9-122">HasBaseIndicies Method</span></span>](icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="8f0c9-123">배열에 기본 인덱스가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-123">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f0c9-124">설명</span><span class="sxs-lookup"><span data-stu-id="8f0c9-124">Remarks</span></span>  

 <span data-ttu-id="8f0c9-125">`ICorDebugArrayValue` 는 1 차원 배열 및 다차원 배열을 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-125">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f0c9-126">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f0c9-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f0c9-127">Requirements</span></span>  

 <span data-ttu-id="8f0c9-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f0c9-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f0c9-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f0c9-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f0c9-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f0c9-131">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f0c9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f0c9-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f0c9-132">See also</span></span>

- [<span data-ttu-id="8f0c9-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f0c9-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
