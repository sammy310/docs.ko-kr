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
ms.openlocfilehash: e55c53b9610dcadee92ba9871bf52e3dacb5796b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726238"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="11703-102">ICorDebugGCReferenceEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="11703-102">ICorDebugGCReferenceEnum::Next Method</span></span>

<span data-ttu-id="11703-103">가비지 수집 되는 개체에 대 한 정보를 포함 하는 지정 된 수의 [COR_GC_REFERENCE](cor-gc-reference-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="11703-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11703-104">구문</span><span class="sxs-lookup"><span data-stu-id="11703-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11703-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11703-105">Parameters</span></span>  

 <span data-ttu-id="11703-106">celt</span><span class="sxs-lookup"><span data-stu-id="11703-106">celt</span></span>  
 <span data-ttu-id="11703-107">진행 검색할 루트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="11703-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="11703-108">루트</span><span class="sxs-lookup"><span data-stu-id="11703-108">roots</span></span>  
 <span data-ttu-id="11703-109">제한이 각각 가비지 수집 될 개체의 루트를 나타내는 [COR_GC_REFERENCE](cor-gc-reference-structure.md) 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="11703-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="11703-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="11703-110">pceltFetched</span></span>  
 <span data-ttu-id="11703-111">제한이 에 실제로 반환 된 [COR_GC_REFERENCE](cor-gc-reference-structure.md) 개체 수에 대 한 포인터 `roots` 입니다.</span><span class="sxs-lookup"><span data-stu-id="11703-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="11703-112">`celt`가 1이면 이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11703-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11703-113">설명</span><span class="sxs-lookup"><span data-stu-id="11703-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11703-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11703-114">Requirements</span></span>  

 <span data-ttu-id="11703-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11703-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11703-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11703-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11703-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11703-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11703-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11703-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11703-119">참조</span><span class="sxs-lookup"><span data-stu-id="11703-119">See also</span></span>

- [<span data-ttu-id="11703-120">ICorDebugGCReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11703-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="11703-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11703-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
