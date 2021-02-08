---
description: '자세히 알아보기: ICorDebugHeapSegmentEnum:: Next 메서드'
title: ICorDebugHeapSegmentEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: 8d2ddfb4df82969fa9cf580ed8a7f903f9d6c260
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803678"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="d7dba-103">ICorDebugHeapSegmentEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="d7dba-103">ICorDebugHeapSegmentEnum::Next Method</span></span>

<span data-ttu-id="d7dba-104">관리 되는 힙의 메모리 영역에 대 한 정보를 포함 하는 지정 된 수의 [COR_SEGMENT](cor-segment-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7dba-104">Gets the specified number of [COR_SEGMENT](cor-segment-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7dba-105">구문</span><span class="sxs-lookup"><span data-stu-id="d7dba-105">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7dba-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7dba-106">Parameters</span></span>  

 <span data-ttu-id="d7dba-107">celt</span><span class="sxs-lookup"><span data-stu-id="d7dba-107">celt</span></span>  
 <span data-ttu-id="d7dba-108">진행 검색할 세그먼트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7dba-108">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="d7dba-109">세그먼트</span><span class="sxs-lookup"><span data-stu-id="d7dba-109">segments</span></span>  
 <span data-ttu-id="d7dba-110">제한이 각각 관리 되는 힙에서 메모리 영역에 대 한 정보를 제공 하는 [COR_SEGMENT](cor-segment-structure.md) 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d7dba-110">[out] An array of pointers, each of which points to a [COR_SEGMENT](cor-segment-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="d7dba-111">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="d7dba-111">pceltFetched</span></span>  
 <span data-ttu-id="d7dba-112">제한이 에 실제로 반환 된 [COR_SEGMENT](cor-segment-structure.md) 개체 수에 대 한 포인터 `segments` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d7dba-112">[out] A pointer to the number of [COR_SEGMENT](cor-segment-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="d7dba-113">`celt`가 1이면 이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dba-113">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7dba-114">설명</span><span class="sxs-lookup"><span data-stu-id="d7dba-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7dba-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7dba-115">Requirements</span></span>  

 <span data-ttu-id="d7dba-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7dba-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7dba-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7dba-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7dba-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7dba-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7dba-119">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7dba-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7dba-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7dba-120">See also</span></span>

- [<span data-ttu-id="d7dba-121">ICorDebugHeapSegmentEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7dba-121">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="d7dba-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7dba-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
