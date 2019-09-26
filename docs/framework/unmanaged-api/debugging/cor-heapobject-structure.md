---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c59ddec655f3127e8dab8d8c41543f03a896cf63
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274029"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="6e473-102">COR_HEAPOBJECT 구조체</span><span class="sxs-lookup"><span data-stu-id="6e473-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="6e473-103">관리되는 힙의 개체에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e473-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e473-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="6e473-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6e473-105">Members</span></span>  
  
|<span data-ttu-id="6e473-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6e473-106">Member</span></span>|<span data-ttu-id="6e473-107">설명</span><span class="sxs-lookup"><span data-stu-id="6e473-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="6e473-108">메모리에 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="6e473-109">개체의 총 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="6e473-110">개체의 유형을 나타내는 [COR_TYPEID](cor-typeid-structure.md) 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-110">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e473-111">설명</span><span class="sxs-lookup"><span data-stu-id="6e473-111">Remarks</span></span>  
 <span data-ttu-id="6e473-112">`COR_HEAPOBJECT`[ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md) 메서드를 호출 하 여 채워지는 [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface 개체를 열거 하 여 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="6e473-113">인스턴스 `COR_HEAPOBJECT` 는 관리 되는 힙에서 라이브 개체에 대 한 정보를 제공 하 고, 개체가 루 팅 되지 않았지만 가비지 수집기에서 아직 수집 되지 않은 개체에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="6e473-114">성능 향상을 `COR_HEAPOBJECT.address` 위해 대부분의 디버깅 API `CORDB_ADDRESS` 에서 사용 되는 ICorDebugValue 인터페이스 값이 아닌 값이 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="6e473-115">지정 된 개체 주소에 대 한 ICorDebugValue 개체를 가져오려면 `CORDB_ADDRESS` [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) 메서드에 값을 전달 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="6e473-116">성능 향상을 `COR_HEAPOBJECT.type` 위해 대부분의 디버깅 API `COR_TYPEID` 에서 사용 되는 ICorDebugType 인터페이스 값이 아닌 값이 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="6e473-117">지정 된 형식 ID에 대 한 ICorDebugType 개체를 가져오려면 `COR_TYPEID` [ICorDebugProcess5:: gettypefortypeid](icordebugprocess5-gettypefortypeid-method.md) 메서드에 값을 전달 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="6e473-118">구조체 `COR_HEAPOBJECT` 에는 참조 횟수가 계산 되는 COM 인터페이스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="6e473-119">`COR_HEAPOBJECT` [ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) 메서드를 호출 하 여 열거자에서 인스턴스를 검색 하는 경우 나중에 참조를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e473-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e473-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e473-120">Requirements</span></span>  
 <span data-ttu-id="6e473-121">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e473-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e473-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e473-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e473-123">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e473-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e473-124">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e473-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e473-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e473-125">See also</span></span>

- [<span data-ttu-id="6e473-126">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="6e473-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="6e473-127">디버깅</span><span class="sxs-lookup"><span data-stu-id="6e473-127">Debugging</span></span>](index.md)
