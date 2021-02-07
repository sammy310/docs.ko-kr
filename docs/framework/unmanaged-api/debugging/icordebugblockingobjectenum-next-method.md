---
description: '자세히 알아보기: ICorDebugBlockingObjectEnum:: Next 메서드'
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
ms.openlocfilehash: 66999ebf333c7115790b56afc1dc1d1ab7c47d69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711819"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="e4229-103">ICorDebugBlockingObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="e4229-103">ICorDebugBlockingObjectEnum::Next Method</span></span>

<span data-ttu-id="e4229-104">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e4229-104">Gets the specified number of [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4229-105">구문</span><span class="sxs-lookup"><span data-stu-id="e4229-105">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4229-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e4229-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="e4229-107">진행 검색할 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e4229-107">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="e4229-108">제한이 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 개체에 대 한 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e4229-108">[out] An array of pointers to [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e4229-109">제한이 검색 된 개체의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e4229-109">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4229-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="e4229-110">Return Value</span></span>  

 <span data-ttu-id="e4229-111">이 메서드는 다음과 같은 특정 HRESULT를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e4229-111">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="e4229-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e4229-112">HRESULT</span></span>|<span data-ttu-id="e4229-113">설명</span><span class="sxs-lookup"><span data-stu-id="e4229-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e4229-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e4229-114">S_OK</span></span>|<span data-ttu-id="e4229-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e4229-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="e4229-116">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e4229-116">S_FALSE</span></span>|<span data-ttu-id="e4229-117">`pceltFetched`이 `celt`와 다른 경우</span><span class="sxs-lookup"><span data-stu-id="e4229-117">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4229-118">설명</span><span class="sxs-lookup"><span data-stu-id="e4229-118">Remarks</span></span>  

 <span data-ttu-id="e4229-119">이 메서드는 일반적인 COM 열거자 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4229-119">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="e4229-120">입력 배열 값의 크기는 이상 이어야 합니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="e4229-120">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="e4229-121">배열은 `celt` 열거형의 다음 값으로 채워지거나, 보다 작은 경우 나머지 모든 값으로 채워집니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="e4229-121">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="e4229-122">이 메서드는 반환 될 때 `pceltFetched` 검색 된 값의 수로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="e4229-122">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="e4229-123">에 `values` 보다 작은 버퍼에 대 한 잘못 된 포인터나 점이 포함 되어 `celt` 있거나 `pceltFetched` 이 잘못 된 포인터인 경우 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4229-123">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4229-124">[CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조를 해제할 필요는 없지만 그 안에 있는 "ICorDebugValue" 인터페이스를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4229-124">Although the [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4229-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4229-125">Requirements</span></span>  

 <span data-ttu-id="e4229-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4229-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4229-127">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4229-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4229-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4229-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4229-129">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4229-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4229-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4229-130">See also</span></span>

- [<span data-ttu-id="e4229-131">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4229-131">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="e4229-132">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4229-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e4229-133">디버깅</span><span class="sxs-lookup"><span data-stu-id="e4229-133">Debugging</span></span>](index.md)
