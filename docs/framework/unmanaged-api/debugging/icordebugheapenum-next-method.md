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
ms.openlocfilehash: f5af8e559b4fbfeb60530372185ca10104ade987
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178857"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="8bcbf-102">ICorDebugHeapEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="8bcbf-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="8bcbf-103">관리되는 힙의 개체에 대한 정보가 포함된 지정된 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bcbf-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bcbf-104">구문</span><span class="sxs-lookup"><span data-stu-id="8bcbf-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bcbf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8bcbf-105">Parameters</span></span>  
 <span data-ttu-id="8bcbf-106">celt</span><span class="sxs-lookup"><span data-stu-id="8bcbf-106">celt</span></span>  
 <span data-ttu-id="8bcbf-107">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8bcbf-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="8bcbf-108">개체</span><span class="sxs-lookup"><span data-stu-id="8bcbf-108">objects</span></span>  
 <span data-ttu-id="8bcbf-109">【아웃】 각 포인터는 관리되는 힙의 개체에 대한 정보를 제공하는 [COR_HEAPOBJECT](cor-heapobject-structure.md) 개체를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="8bcbf-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="8bcbf-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="8bcbf-110">pceltFetched</span></span>  
 <span data-ttu-id="8bcbf-111">【아웃】 실제로 반환된 [COR_HEAPOBJECT](cor-heapobject-structure.md) 개체 수에 `objects`대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8bcbf-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="8bcbf-112">`celt`가 1이면 이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bcbf-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bcbf-113">설명</span><span class="sxs-lookup"><span data-stu-id="8bcbf-113">Remarks</span></span>  
 <span data-ttu-id="8bcbf-114">`COR_HEAPOBJECT.type` 필드는 중첩된 참조 수가 계산되는 COM 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8bcbf-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="8bcbf-115">이 참조는 `ICorDebugHeapEnum::Next` 호출자가 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bcbf-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bcbf-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bcbf-116">Requirements</span></span>  
 <span data-ttu-id="8bcbf-117">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bcbf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bcbf-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bcbf-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bcbf-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bcbf-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bcbf-120">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bcbf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bcbf-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bcbf-121">See also</span></span>

- [<span data-ttu-id="8bcbf-122">ICorDebugHeapEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bcbf-122">ICorDebugHeapEnum Interface</span></span>](icordebugheapenum-interface.md)
- [<span data-ttu-id="8bcbf-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bcbf-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
