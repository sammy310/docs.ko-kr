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
ms.openlocfilehash: 232068a5fee8f7bd3dfbddf4d9452e80d6fd6170
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719192"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="d7a73-102">ICorDebugBlockingObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a73-102">ICorDebugBlockingObjectEnum::Next Method</span></span>

<span data-ttu-id="d7a73-103">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7a73-103">Gets the specified number of [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7a73-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7a73-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7a73-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7a73-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="d7a73-106">진행 검색할 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a73-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="d7a73-107">제한이 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 개체에 대 한 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a73-107">[out] An array of pointers to [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d7a73-108">제한이 검색 된 개체의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a73-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7a73-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="d7a73-109">Return Value</span></span>  

 <span data-ttu-id="d7a73-110">이 메서드는 다음과 같은 특정 HRESULT를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a73-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="d7a73-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7a73-111">HRESULT</span></span>|<span data-ttu-id="d7a73-112">설명</span><span class="sxs-lookup"><span data-stu-id="d7a73-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7a73-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7a73-113">S_OK</span></span>|<span data-ttu-id="d7a73-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a73-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="d7a73-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d7a73-115">S_FALSE</span></span>|<span data-ttu-id="d7a73-116">`pceltFetched`이 `celt`와 다른 경우</span><span class="sxs-lookup"><span data-stu-id="d7a73-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7a73-117">설명</span><span class="sxs-lookup"><span data-stu-id="d7a73-117">Remarks</span></span>  

 <span data-ttu-id="d7a73-118">이 메서드는 일반적인 COM 열거자 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a73-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="d7a73-119">입력 배열 값의 크기는 이상 이어야 합니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="d7a73-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="d7a73-120">배열은 `celt` 열거형의 다음 값으로 채워지거나, 보다 작은 경우 나머지 모든 값으로 채워집니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="d7a73-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="d7a73-121">이 메서드는 반환 될 때 `pceltFetched` 검색 된 값의 수로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d7a73-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="d7a73-122">에 `values` 보다 작은 버퍼에 대 한 잘못 된 포인터나 점이 포함 되어 `celt` 있거나 `pceltFetched` 이 잘못 된 포인터인 경우 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a73-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7a73-123">[CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조를 해제할 필요는 없지만 그 안에 있는 "ICorDebugValue" 인터페이스를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a73-123">Although the [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7a73-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7a73-124">Requirements</span></span>  

 <span data-ttu-id="d7a73-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7a73-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7a73-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7a73-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7a73-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7a73-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7a73-128">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7a73-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a73-129">참조</span><span class="sxs-lookup"><span data-stu-id="d7a73-129">See also</span></span>

- [<span data-ttu-id="d7a73-130">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7a73-130">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="d7a73-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7a73-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d7a73-132">디버깅</span><span class="sxs-lookup"><span data-stu-id="d7a73-132">Debugging</span></span>](index.md)
