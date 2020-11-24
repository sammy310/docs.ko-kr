---
title: ICorDebugProcess5::EnumerateHeapRegions 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
ms.openlocfilehash: 5a51670200f8fc8a98ff7b80334253b37c7d89ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671124"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="37734-102">ICorDebugProcess5::EnumerateHeapRegions 메서드</span><span class="sxs-lookup"><span data-stu-id="37734-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>

<span data-ttu-id="37734-103">관리 되는 힙의 메모리 범위에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37734-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37734-104">구문</span><span class="sxs-lookup"><span data-stu-id="37734-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37734-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37734-105">Parameters</span></span>  

 `ppRegions`  
 <span data-ttu-id="37734-106">제한이 개체가 관리 되는 힙에서 상주 하는 메모리 범위에 대 한 열거자 인 [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37734-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37734-107">설명</span><span class="sxs-lookup"><span data-stu-id="37734-107">Remarks</span></span>  

 <span data-ttu-id="37734-108">메서드를 호출 하기 전에 `ICorDebugProcess5::EnumerateHeapRegions` [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) 메서드를 호출 하 고 `areGCStructuresValid` 반환 된 [COR_HEAPINFO](cor-heapinfo-structure.md) 개체의 필드 값을 검사 하 여 현재 상태에서 가비지 컬렉션 힙을 열거 가능 하 게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37734-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="37734-109">또한이 메서드는 `ICorDebugProcess5::EnumerateHeapRegions` `E_FAIL` 메모리 영역이 만들어지기 전에 프로세스의 수명 중 너무 이른 시간에 연결 하는 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37734-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="37734-110">이 메서드는 관리 되는 개체를 포함할 수 있는 모든 메모리 영역을 열거 하지만 관리 되는 개체가 실제로 해당 지역에 있음을 보장 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37734-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="37734-111">[ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) collection 개체는 비어 있거나 예약 된 메모리 영역을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37734-111">The [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="37734-112">[ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface 개체는 개체 [COR_SEGMENT](cor-segment-structure.md) 열거할 수 있도록 하는 ICorDebugEnum 인터페이스에서 파생 된 표준 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="37734-112">The [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](cor-segment-structure.md) objects.</span></span> <span data-ttu-id="37734-113">각 [COR_SEGMENT](cor-segment-structure.md) 개체는 해당 세그먼트의 개체 생성과 함께 특정 세그먼트의 메모리 범위에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="37734-113">Each [COR_SEGMENT](cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37734-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37734-114">Requirements</span></span>  

 <span data-ttu-id="37734-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37734-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37734-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37734-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37734-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37734-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37734-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37734-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37734-119">참조</span><span class="sxs-lookup"><span data-stu-id="37734-119">See also</span></span>

- [<span data-ttu-id="37734-120">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37734-120">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="37734-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37734-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
