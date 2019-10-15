---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc0b67621f77c0741e0b63b84ab1794530d6280b
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274231"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="eddc3-102">COR_GC_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="eddc3-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="eddc3-103">가비지 수집할 개체에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eddc3-104">구문</span><span class="sxs-lookup"><span data-stu-id="eddc3-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="eddc3-105">멤버</span><span class="sxs-lookup"><span data-stu-id="eddc3-105">Members</span></span>  
  
|<span data-ttu-id="eddc3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="eddc3-106">Member</span></span>|<span data-ttu-id="eddc3-107">설명</span><span class="sxs-lookup"><span data-stu-id="eddc3-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="eddc3-108">핸들이 나 개체가 속한 응용 프로그램 도메인에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="eddc3-109">값은 일 `null`수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="eddc3-110">가비지 수집 될 개체에 해당 하는 ICorDebugValue 또는 ICorDebugReferenceValue 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="eddc3-111">루트의 출처를 나타내는 [CorGCReferenceType](corgcreferencetype-enumeration.md) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="eddc3-112">자세한 내용은 설명 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eddc3-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="eddc3-113">가비지 수집 될 개체에 대 한 추가 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="eddc3-114">이 정보는 `type` 필드에 표시 되는 개체의 원본에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="eddc3-115">자세한 내용은 설명 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eddc3-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eddc3-116">설명</span><span class="sxs-lookup"><span data-stu-id="eddc3-116">Remarks</span></span>  
 <span data-ttu-id="eddc3-117">`type` 필드는 참조의 출처를 나타내는 [CorGCReferenceType](corgcreferencetype-enumeration.md) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="eddc3-118">특정 `COR_GC_REFERENCE` 값은 다음과 같은 종류의 관리 되는 개체를 반영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="eddc3-119">모든 관리 되는 스택 (`CorGCReferenceType.CorReferenceStack`)의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="eddc3-120">여기에는 공용 언어 런타임에서 만든 개체 뿐만 아니라 관리 코드의 라이브 참조도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="eddc3-121">핸들 테이블 (`CorGCReferenceType.CorHandle*`)의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="eddc3-122">여기에는 모듈의`HNDTYPE_STRONG` 강력한 `HNDTYPE_REFCOUNT`참조 (및) 및 정적 변수가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="eddc3-123">종료자 큐 (`CorGCReferenceType.CorReferenceFinalizer`)의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="eddc3-124">종료자는 종료 자가 실행 될 때까지 개체를 큐에 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="eddc3-125">필드 `extraData` 에는 참조의 원본 (또는 형식)에 따라 추가 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="eddc3-126">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-126">Possible values are:</span></span>  
  
- <span data-ttu-id="eddc3-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="eddc3-127">`DependentSource`.</span></span> <span data-ttu-id="eddc3-128">가 이면이 필드는 활성 상태인 경우에서 `COR_GC_REFERENCE.Location`가비지 수집 될 개체의 루트를 나타내는 개체입니다. `CorGCREferenceType.CorHandleStrongDependent` `type`</span><span class="sxs-lookup"><span data-stu-id="eddc3-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="eddc3-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="eddc3-129">`RefCount`.</span></span> <span data-ttu-id="eddc3-130">`type` 가`CorGCREferenceType.CorHandleStrongRefCount`이면이 필드는 핸들의 참조 수입니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="eddc3-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="eddc3-131">`Size`.</span></span> <span data-ttu-id="eddc3-132">`type` 이 인 `CorGCREferenceType.CorHandleStrongSizedByref`경우이 필드는 가비지 수집기가 개체 루트를 계산 하는 개체 트리의 마지막 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="eddc3-133">이 계산은 반드시 최신 상태를 유지 해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="eddc3-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eddc3-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eddc3-134">Requirements</span></span>  
 <span data-ttu-id="eddc3-135">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eddc3-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eddc3-136">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eddc3-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eddc3-137">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eddc3-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eddc3-138">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eddc3-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eddc3-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eddc3-139">See also</span></span>

- [<span data-ttu-id="eddc3-140">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="eddc3-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="eddc3-141">디버깅</span><span class="sxs-lookup"><span data-stu-id="eddc3-141">Debugging</span></span>](index.md)
