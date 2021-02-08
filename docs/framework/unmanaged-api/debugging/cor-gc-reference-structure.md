---
description: '다음에 대 한 자세한 정보: COR_GC_REFERENCE 구조체'
title: COR_GC_REFERENCE 구조체
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
ms.openlocfilehash: 38518bb1eb870081621bf32af9e63cdaa208dbd3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801815"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="4ace5-103">COR_GC_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="4ace5-103">COR_GC_REFERENCE Structure</span></span>

<span data-ttu-id="4ace5-104">가비지 수집할 개체에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-104">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ace5-105">구문</span><span class="sxs-lookup"><span data-stu-id="4ace5-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="4ace5-106">구성원</span><span class="sxs-lookup"><span data-stu-id="4ace5-106">Members</span></span>  
  
|<span data-ttu-id="4ace5-107">멤버</span><span class="sxs-lookup"><span data-stu-id="4ace5-107">Member</span></span>|<span data-ttu-id="4ace5-108">설명</span><span class="sxs-lookup"><span data-stu-id="4ace5-108">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="4ace5-109">핸들이 나 개체가 속한 응용 프로그램 도메인에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-109">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="4ace5-110">값은 일 수 있습니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="4ace5-110">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="4ace5-111">가비지 수집 될 개체에 해당 하는 ICorDebugValue 또는 ICorDebugReferenceValue 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-111">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="4ace5-112">루트의 출처를 나타내는 [CorGCReferenceType](corgcreferencetype-enumeration.md) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-112">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="4ace5-113">자세한 내용은 주의 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ace5-113">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="4ace5-114">가비지 수집 될 개체에 대 한 추가 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-114">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="4ace5-115">이 정보는 필드에 표시 되는 개체의 원본에 따라 달라 집니다 `type` .</span><span class="sxs-lookup"><span data-stu-id="4ace5-115">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="4ace5-116">자세한 내용은 주의 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ace5-116">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ace5-117">설명</span><span class="sxs-lookup"><span data-stu-id="4ace5-117">Remarks</span></span>  

 <span data-ttu-id="4ace5-118">`type`필드는 참조의 출처를 나타내는 [CorGCReferenceType](corgcreferencetype-enumeration.md) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-118">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="4ace5-119">특정 `COR_GC_REFERENCE` 값은 다음과 같은 종류의 관리 되는 개체를 반영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-119">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="4ace5-120">모든 관리 되는 스택 ( `CorGCReferenceType.CorReferenceStack` )의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-120">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="4ace5-121">여기에는 공용 언어 런타임에서 만든 개체 뿐만 아니라 관리 코드의 라이브 참조도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-121">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="4ace5-122">핸들 테이블 ()의 개체 `CorGCReferenceType.CorHandle*` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-122">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="4ace5-123">여기에는 모듈의 강력한 참조 ( `HNDTYPE_STRONG` 및 `HNDTYPE_REFCOUNT` ) 및 정적 변수가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-123">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="4ace5-124">종료자 큐 ()의 개체 `CorGCReferenceType.CorReferenceFinalizer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-124">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="4ace5-125">종료자는 종료 자가 실행 될 때까지 개체를 큐에 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-125">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="4ace5-126">필드에는 `extraData` 참조의 원본 (또는 형식)에 따라 추가 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-126">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="4ace5-127">가능한 값은</span><span class="sxs-lookup"><span data-stu-id="4ace5-127">Possible values are:</span></span>  
  
- <span data-ttu-id="4ace5-128">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="4ace5-128">`DependentSource`.</span></span> <span data-ttu-id="4ace5-129">가 이면 `type` `CorGCREferenceType.CorHandleStrongDependent` 이 필드는 활성 상태인 경우에서 가비지 수집 될 개체의 루트를 나타내는 개체입니다 `COR_GC_REFERENCE.Location` .</span><span class="sxs-lookup"><span data-stu-id="4ace5-129">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="4ace5-130">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="4ace5-130">`RefCount`.</span></span> <span data-ttu-id="4ace5-131">가 이면 `type` `CorGCREferenceType.CorHandleStrongRefCount` 이 필드는 핸들의 참조 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-131">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="4ace5-132">`Size`.</span><span class="sxs-lookup"><span data-stu-id="4ace5-132">`Size`.</span></span> <span data-ttu-id="4ace5-133">`type`이 인 경우 `CorGCREferenceType.CorHandleStrongSizedByref` 이 필드는 가비지 수집기가 개체 루트를 계산 하는 개체 트리의 마지막 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-133">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="4ace5-134">이 계산은 반드시 최신 상태를 유지 해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4ace5-134">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ace5-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ace5-135">Requirements</span></span>  

 <span data-ttu-id="4ace5-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ace5-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ace5-137">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ace5-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ace5-138">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ace5-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ace5-139">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ace5-139">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ace5-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ace5-140">See also</span></span>

- [<span data-ttu-id="4ace5-141">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="4ace5-141">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="4ace5-142">디버깅</span><span class="sxs-lookup"><span data-stu-id="4ace5-142">Debugging</span></span>](index.md)
