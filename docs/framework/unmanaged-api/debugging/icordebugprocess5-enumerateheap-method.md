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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b404b7762e085eb44f0bd3b448fcee9eab9a3c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948787"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="7db05-102">ICorDebugProcess5::EnumerateHeap 메서드</span><span class="sxs-lookup"><span data-stu-id="7db05-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="7db05-103">관리 되는 힙의 개체에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7db05-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7db05-104">구문</span><span class="sxs-lookup"><span data-stu-id="7db05-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7db05-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7db05-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="7db05-106">[out] 주소에 대 한 포인터를 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 인터페이스 개체는 관리 되는 힙에 있는 개체에 대 한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="7db05-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7db05-107">설명</span><span class="sxs-lookup"><span data-stu-id="7db05-107">Remarks</span></span>  
 <span data-ttu-id="7db05-108">호출 하기 전에 합니다 `ICorDebugProcess5::EnumerateHeap` 호출 해야 합니다는 [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) 메서드의 값을 검사 합니다 `areGCStructuresValid` 반환 된 필드 [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) 가비지 수집 힙의 현재 상태에서 열거 가능한 지 확인 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7db05-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="7db05-109">또한 합니다 `ICorDebugProcess5::EnumerateHeap` 반환 `E_FAIL` 관리 되는 힙 할당에 대 한 너무 일찍 메모리 하기 전에 프로세스의 수명에에서 연결 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="7db05-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="7db05-110">합니다 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 인터페이스 개체는 열거할 수 있도록 ICorDebugEnum 인터페이스에서 파생 하는 표준 열거자 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7db05-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="7db05-111">이 메서드는 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 사용 하 여 컬렉션 개체 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 모든 개체에 대 한 정보를 제공 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="7db05-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="7db05-112">컬렉션을 포함할 수도 있습니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 으로 없습니다 루트인 개체에 대 한 정보를 제공 하는 인스턴스 개체 하지만 가비지 수집기에 의해 아직 수집 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="7db05-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7db05-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7db05-113">Requirements</span></span>  
 <span data-ttu-id="7db05-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7db05-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7db05-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7db05-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7db05-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7db05-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7db05-117">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7db05-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7db05-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="7db05-118">See also</span></span>

- [<span data-ttu-id="7db05-119">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7db05-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="7db05-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7db05-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
