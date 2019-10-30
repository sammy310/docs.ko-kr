---
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
ms.openlocfilehash: 1beb69bfaad9acb9c269ad8becb81bea64edb6a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138465"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="5e6e5-102">ICorDebugHeapEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="5e6e5-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="5e6e5-103">관리 되는 힙의 개체에 대 한 정보를 포함 하는 지정 된 수의 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5e6e5-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e6e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="5e6e5-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e6e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5e6e5-105">Parameters</span></span>  
 <span data-ttu-id="5e6e5-106">celt</span><span class="sxs-lookup"><span data-stu-id="5e6e5-106">celt</span></span>  
 <span data-ttu-id="5e6e5-107">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6e5-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="5e6e5-108">개체</span><span class="sxs-lookup"><span data-stu-id="5e6e5-108">objects</span></span>  
 <span data-ttu-id="5e6e5-109">제한이 각각 관리 되는 힙의 개체에 대 한 정보를 제공 하는 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6e5-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="5e6e5-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="5e6e5-110">pceltFetched</span></span>  
 <span data-ttu-id="5e6e5-111">제한이 `objects`에서 실제로 반환 된 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개체 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6e5-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="5e6e5-112">`celt`가 1이면 이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e6e5-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e6e5-113">주의</span><span class="sxs-lookup"><span data-stu-id="5e6e5-113">Remarks</span></span>  
 <span data-ttu-id="5e6e5-114">`COR_HEAPOBJECT.type` 필드는 중첩된 참조 수가 계산되는 COM 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6e5-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="5e6e5-115">이 참조는 `ICorDebugHeapEnum::Next` 호출자가 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6e5-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e6e5-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5e6e5-116">Requirements</span></span>  
 <span data-ttu-id="5e6e5-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e6e5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e6e5-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e6e5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e6e5-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e6e5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e6e5-120">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e6e5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e6e5-121">참조</span><span class="sxs-lookup"><span data-stu-id="5e6e5-121">See also</span></span>

- [<span data-ttu-id="5e6e5-122">ICorDebugHeapEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e6e5-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)
- [<span data-ttu-id="5e6e5-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e6e5-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
