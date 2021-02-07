---
description: '자세히 알아보기: ICorDebugHeapEnum:: Next 메서드'
title: ICorDebugHeapEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: 22e81b9b0c4ac2027f932187b6f860d08adf6f97
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691954"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="31c46-103">ICorDebugHeapEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="31c46-103">ICorDebugHeapEnum::Next Method</span></span>

<span data-ttu-id="31c46-104">관리 되는 힙의 개체에 대 한 정보를 포함 하는 지정 된 수의 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31c46-104">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31c46-105">구문</span><span class="sxs-lookup"><span data-stu-id="31c46-105">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31c46-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="31c46-106">Parameters</span></span>  

 <span data-ttu-id="31c46-107">celt</span><span class="sxs-lookup"><span data-stu-id="31c46-107">celt</span></span>  
 <span data-ttu-id="31c46-108">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="31c46-108">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="31c46-109">개체</span><span class="sxs-lookup"><span data-stu-id="31c46-109">objects</span></span>  
 <span data-ttu-id="31c46-110">제한이 각각 관리 되는 힙의 개체에 대 한 정보를 제공 하는 [COR_HEAPOBJECT](cor-heapobject-structure.md) 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="31c46-110">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="31c46-111">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="31c46-111">pceltFetched</span></span>  
 <span data-ttu-id="31c46-112">제한이 에 실제로 반환 된 [COR_HEAPOBJECT](cor-heapobject-structure.md) 개체 수에 대 한 포인터 `objects` 입니다.</span><span class="sxs-lookup"><span data-stu-id="31c46-112">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="31c46-113">`celt`가 1이면 이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31c46-113">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31c46-114">설명</span><span class="sxs-lookup"><span data-stu-id="31c46-114">Remarks</span></span>  

 <span data-ttu-id="31c46-115">`COR_HEAPOBJECT.type` 필드는 중첩된 참조 수가 계산되는 COM 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="31c46-115">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="31c46-116">이 참조는 `ICorDebugHeapEnum::Next` 호출자가 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c46-116">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31c46-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="31c46-117">Requirements</span></span>  

 <span data-ttu-id="31c46-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31c46-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31c46-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31c46-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31c46-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31c46-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31c46-121">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31c46-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31c46-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31c46-122">See also</span></span>

- [<span data-ttu-id="31c46-123">ICorDebugHeapEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31c46-123">ICorDebugHeapEnum Interface</span></span>](icordebugheapenum-interface.md)
- [<span data-ttu-id="31c46-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31c46-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
