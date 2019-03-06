---
title: ICorDebugBlockingObjectEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccab0f311e51c0e82998b58f75f38359271065e3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493143"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="87a98-102">ICorDebugBlockingObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="87a98-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="87a98-103">지정 된 개수를 가져옵니다 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 개체를 열거형에서 현재 위치에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a98-104">구문</span><span class="sxs-lookup"><span data-stu-id="87a98-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="87a98-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87a98-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="87a98-106">[in] 검색할 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="87a98-107">[out] 에 대 한 포인터의 배열을 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="87a98-108">[out] 검색 된 개체의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87a98-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="87a98-109">Return Value</span></span>  
 <span data-ttu-id="87a98-110">이 메서드는 다음과 같은 특정 HRESULT를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="87a98-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87a98-111">HRESULT</span></span>|<span data-ttu-id="87a98-112">설명</span><span class="sxs-lookup"><span data-stu-id="87a98-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87a98-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="87a98-113">S_OK</span></span>|<span data-ttu-id="87a98-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="87a98-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="87a98-115">S_FALSE</span></span>|<span data-ttu-id="87a98-116">`pceltFetched`이 `celt`와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87a98-117">설명</span><span class="sxs-lookup"><span data-stu-id="87a98-117">Remarks</span></span>  
 <span data-ttu-id="87a98-118">이 메서드가 함수는 일반적인 COM 열거자를 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="87a98-119">입력된 배열 값 이상 이어야 합니다 크기인 `celt`합니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="87a98-120">배열 채워집니다 중 하나를 사용 하 여 다음 `celt` 값을 열거형에 남아 있는 모든 값 보다 적으면 `celt` 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="87a98-121">이 메서드는 반환 될 때 `pceltFetched` 검색 된 값의 수로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="87a98-122">경우 `values` 잘못 된 포인터를 포함 하거나 보다 작은 버퍼를 가리키는 `celt`, 또는 경우 `pceltFetched` 는 잘못 된 포인터는 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87a98-123">하지만 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조를 해제할 필요가 없습니다, 내부 "ICorDebugValue" 인터페이스는 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a98-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87a98-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87a98-124">Requirements</span></span>  
 <span data-ttu-id="87a98-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="87a98-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87a98-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87a98-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87a98-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87a98-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87a98-128">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87a98-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a98-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="87a98-129">See also</span></span>
- [<span data-ttu-id="87a98-130">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87a98-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="87a98-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87a98-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="87a98-132">디버깅</span><span class="sxs-lookup"><span data-stu-id="87a98-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
