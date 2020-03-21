---
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
ms.openlocfilehash: 8a267ec7123edb73ad51f0781a78344119ec6f21
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178887"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="366f7-102">ICorDebugHeapSegmentEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="366f7-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="366f7-103">관리되는 힙의 메모리 영역에 대한 정보가 포함된 [지정된 COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="366f7-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="366f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="366f7-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="366f7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="366f7-105">Parameters</span></span>  
 <span data-ttu-id="366f7-106">celt</span><span class="sxs-lookup"><span data-stu-id="366f7-106">celt</span></span>  
 <span data-ttu-id="366f7-107">【인】 검색할 세그먼트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="366f7-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="366f7-108">세그먼트</span><span class="sxs-lookup"><span data-stu-id="366f7-108">segments</span></span>  
 <span data-ttu-id="366f7-109">【아웃】 포인터의 배열, 각각관리 되는 힙에서 메모리 영역에 대 한 정보를 제공 하는 [COR_HEAPOBJECT](cor-heapobject-structure.md) 개체를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="366f7-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="366f7-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="366f7-110">pceltFetched</span></span>  
 <span data-ttu-id="366f7-111">【아웃】 실제로 반환된 [COR_HEAPOBJECT](cor-heapobject-structure.md) 개체 수에 `segments`대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="366f7-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="366f7-112">`celt`가 1이면 이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="366f7-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="366f7-113">설명</span><span class="sxs-lookup"><span data-stu-id="366f7-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="366f7-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="366f7-114">Requirements</span></span>  
 <span data-ttu-id="366f7-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="366f7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="366f7-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="366f7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="366f7-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="366f7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="366f7-118">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="366f7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="366f7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="366f7-119">See also</span></span>

- [<span data-ttu-id="366f7-120">ICorDebugHeapSegmentEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="366f7-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="366f7-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="366f7-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
