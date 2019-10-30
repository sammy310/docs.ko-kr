---
title: ICorDebugProcess5::EnumerateHeap 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
ms.openlocfilehash: c8cfc9cdf6580a002f6ac15080012a9e8c63be20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129657"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="f1971-102">ICorDebugProcess5::EnumerateHeap 메서드</span><span class="sxs-lookup"><span data-stu-id="f1971-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="f1971-103">관리 되는 힙의 개체에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f1971-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1971-104">구문</span><span class="sxs-lookup"><span data-stu-id="f1971-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1971-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1971-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="f1971-106">제한이 관리 되는 힙에 있는 개체의 열거자 인 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f1971-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1971-107">주의</span><span class="sxs-lookup"><span data-stu-id="f1971-107">Remarks</span></span>  
 <span data-ttu-id="f1971-108">`ICorDebugProcess5::EnumerateHeap` 메서드를 호출 하기 전에 [ICorDebugProcess5:: GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) 메서드를 호출 하 고 반환 된 [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) 개체의 `areGCStructuresValid` 필드 값을 검사 하 여 해당 개체의 가비지 수집 힙이 현재 상태는 열거 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1971-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="f1971-109">또한 관리 되는 힙의 메모리를 할당 하기 전에 프로세스의 수명 동안 너무 일찍 연결 하는 경우에는 `ICorDebugProcess5::EnumerateHeap` `E_FAIL`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1971-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="f1971-110">[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface 개체는 ICorDebugEnum 인터페이스에서 파생 된 표준 열거자로, [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개체를 열거 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1971-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="f1971-111">이 메서드는 모든 개체에 대 한 정보를 제공 하는 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 인스턴스로 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection 개체를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="f1971-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="f1971-112">컬렉션에는 개체에 의해 루 지는 않지만 가비지 수집기에서 아직 수집 되지 않은 개체에 대 한 정보를 제공 하는 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 인스턴스가 포함 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1971-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1971-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1971-113">Requirements</span></span>  
 <span data-ttu-id="f1971-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1971-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1971-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1971-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1971-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1971-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1971-117">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1971-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1971-118">참조</span><span class="sxs-lookup"><span data-stu-id="f1971-118">See also</span></span>

- [<span data-ttu-id="f1971-119">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1971-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="f1971-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1971-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
