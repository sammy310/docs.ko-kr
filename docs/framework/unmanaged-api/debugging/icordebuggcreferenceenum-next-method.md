---
title: ICorDebugGCReferenceEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33ad221f2a05357484d0877b6306d78e3864eff6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120174"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="c8c60-102">ICorDebugGCReferenceEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="c8c60-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="c8c60-103">지정 된 개수를 가져옵니다 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 가비지 수집 될 개체에 대 한 정보가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c8c60-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c60-104">구문</span><span class="sxs-lookup"><span data-stu-id="c8c60-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8c60-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8c60-105">Parameters</span></span>  
 <span data-ttu-id="c8c60-106">celt</span><span class="sxs-lookup"><span data-stu-id="c8c60-106">celt</span></span>  
 <span data-ttu-id="c8c60-107">[in] 검색할 루트의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8c60-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="c8c60-108">루트</span><span class="sxs-lookup"><span data-stu-id="c8c60-108">roots</span></span>  
 <span data-ttu-id="c8c60-109">[out] 각각 가리키는 포인터 배열을 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 가비지가 수집 되기를 개체의 루트를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c8c60-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="c8c60-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="c8c60-110">pceltFetched</span></span>  
 <span data-ttu-id="c8c60-111">[out] 개수에 대 한 포인터 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 개체에 실제로 반환 된 `roots`합니다.</span><span class="sxs-lookup"><span data-stu-id="c8c60-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="c8c60-112">`celt`가 1이면 이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8c60-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8c60-113">설명</span><span class="sxs-lookup"><span data-stu-id="c8c60-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8c60-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8c60-114">Requirements</span></span>  
 <span data-ttu-id="c8c60-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8c60-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8c60-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8c60-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8c60-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8c60-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8c60-118">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8c60-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c60-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8c60-119">See also</span></span>

- [<span data-ttu-id="c8c60-120">ICorDebugGCReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8c60-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="c8c60-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8c60-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
