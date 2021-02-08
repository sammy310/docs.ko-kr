---
description: '다음에 대 한 자세한 정보: COR_HEAPOBJECT 구조체'
title: COR_HEAPOBJECT 구조체
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
ms.openlocfilehash: f41e02e7c528063f4b7ed485cbadbabb4d3e5ca7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801802"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="d6a4a-103">COR_HEAPOBJECT 구조체</span><span class="sxs-lookup"><span data-stu-id="d6a4a-103">COR_HEAPOBJECT Structure</span></span>

<span data-ttu-id="d6a4a-104">관리되는 힙의 개체에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-104">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6a4a-105">구문</span><span class="sxs-lookup"><span data-stu-id="d6a4a-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="d6a4a-106">구성원</span><span class="sxs-lookup"><span data-stu-id="d6a4a-106">Members</span></span>  
  
|<span data-ttu-id="d6a4a-107">멤버</span><span class="sxs-lookup"><span data-stu-id="d6a4a-107">Member</span></span>|<span data-ttu-id="d6a4a-108">설명</span><span class="sxs-lookup"><span data-stu-id="d6a4a-108">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="d6a4a-109">메모리에 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-109">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="d6a4a-110">개체의 총 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-110">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="d6a4a-111">개체의 형식을 나타내는 [COR_TYPEID](cor-typeid-structure.md) 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-111">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6a4a-112">설명</span><span class="sxs-lookup"><span data-stu-id="d6a4a-112">Remarks</span></span>  

 <span data-ttu-id="d6a4a-113">`COR_HEAPOBJECT`[ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md) 메서드를 호출 하 여 채워지는 [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface 개체를 열거 하 여 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-113">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="d6a4a-114">`COR_HEAPOBJECT`인스턴스는 관리 되는 힙에서 라이브 개체에 대 한 정보를 제공 하 고, 개체가 루 팅 되지 않았지만 가비지 수집기에서 아직 수집 되지 않은 개체에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-114">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="d6a4a-115">성능 향상을 위해 `COR_HEAPOBJECT.address` `CORDB_ADDRESS` 대부분의 디버깅 API에서 사용 되는 ICorDebugValue 인터페이스 값이 아닌 값이 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-115">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="d6a4a-116">지정 된 개체 주소에 대 한 ICorDebugValue 개체를 가져오려면 `CORDB_ADDRESS` [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) 메서드에 값을 전달 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-116">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="d6a4a-117">성능 향상을 위해 `COR_HEAPOBJECT.type` `COR_TYPEID` 대부분의 디버깅 API에서 사용 되는 ICorDebugType 인터페이스 값이 아닌 값이 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-117">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="d6a4a-118">지정 된 형식 ID에 대 한 ICorDebugType 개체를 가져오려면 `COR_TYPEID` [ICorDebugProcess5:: GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) 메서드에 값을 전달 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-118">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="d6a4a-119">구조체에는 `COR_HEAPOBJECT` 참조 횟수가 계산 되는 COM 인터페이스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-119">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="d6a4a-120">`COR_HEAPOBJECT` [ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) 메서드를 호출 하 여 열거자에서 인스턴스를 검색 하는 경우 나중에 참조를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-120">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6a4a-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6a4a-121">Requirements</span></span>  

 <span data-ttu-id="d6a4a-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6a4a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6a4a-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6a4a-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6a4a-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6a4a-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6a4a-125">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6a4a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6a4a-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6a4a-126">See also</span></span>

- [<span data-ttu-id="d6a4a-127">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="d6a4a-127">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="d6a4a-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="d6a4a-128">Debugging</span></span>](index.md)
