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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a9e423a35ba8c592bbfd806f9087a88ee251e76
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502289"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="2b6b8-102">ICorDebugHeapEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="2b6b8-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="2b6b8-103">지정 된 개수를 가져옵니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 관리 되는 힙의 개체에 대 한 정보가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="2b6b8-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b6b8-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b6b8-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b6b8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b6b8-105">Parameters</span></span>  
 <span data-ttu-id="2b6b8-106">celt</span><span class="sxs-lookup"><span data-stu-id="2b6b8-106">celt</span></span>  
 <span data-ttu-id="2b6b8-107">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6b8-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="2b6b8-108">개체</span><span class="sxs-lookup"><span data-stu-id="2b6b8-108">objects</span></span>  
 <span data-ttu-id="2b6b8-109">[out] 각각 가리키는 포인터 배열을 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 관리 되는 힙의 개체에 대 한 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6b8-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="2b6b8-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="2b6b8-110">pceltFetched</span></span>  
 <span data-ttu-id="2b6b8-111">[out] 개수에 대 한 포인터 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개체에 실제로 반환 된 `objects`합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6b8-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="2b6b8-112">
  `celt\`가 1이면 이 값은 `null\`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6b8-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b6b8-113">설명</span><span class="sxs-lookup"><span data-stu-id="2b6b8-113">Remarks</span></span>  
 <span data-ttu-id="2b6b8-114">
  `COR_HEAPOBJECT.type\` 필드는 중첩된 참조 수가 계산되는 COM 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6b8-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="2b6b8-115">이 참조는 `ICorDebugHeapEnum::Next` 호출자가 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6b8-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b6b8-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b6b8-116">Requirements</span></span>  
 <span data-ttu-id="2b6b8-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b6b8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b6b8-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b6b8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b6b8-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b6b8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b6b8-120">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b6b8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b6b8-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b6b8-121">See also</span></span>
- [<span data-ttu-id="2b6b8-122">ICorDebugHeapEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b6b8-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)
- [<span data-ttu-id="2b6b8-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b6b8-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
