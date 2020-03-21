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
ms.openlocfilehash: e22269b76c230f702f4712298fddcd0df1fde50d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179321"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="1bc08-102">COR_GC_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="1bc08-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="1bc08-103">가비지 수집할 개체에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bc08-104">구문</span><span class="sxs-lookup"><span data-stu-id="1bc08-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="1bc08-105">구성원</span><span class="sxs-lookup"><span data-stu-id="1bc08-105">Members</span></span>  
  
|<span data-ttu-id="1bc08-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1bc08-106">Member</span></span>|<span data-ttu-id="1bc08-107">Description</span><span class="sxs-lookup"><span data-stu-id="1bc08-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="1bc08-108">핸들 또는 개체가 속한 응용 프로그램 도메인에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="1bc08-109">해당 값은 `null`할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="1bc08-110">ICorDebugValue 또는 가비지 수집할 개체에 해당하는 ICorDebugReferenceValue 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="1bc08-111">루트의 위치를 나타내는 [CorGCReferenceType](corgcreferencetype-enumeration.md) 열거 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="1bc08-112">자세한 내용은 주의 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc08-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="1bc08-113">가비지 수집할 개체에 대한 추가 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="1bc08-114">이 정보는 필드에 표시된 대로 개체의 소스에 `type` 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="1bc08-115">자세한 내용은 주의 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc08-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bc08-116">설명</span><span class="sxs-lookup"><span data-stu-id="1bc08-116">Remarks</span></span>  
 <span data-ttu-id="1bc08-117">`type` 필드는 참조가 발생한 위치를 나타내는 [CorGCReferenceType](corgcreferencetype-enumeration.md) 열거 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="1bc08-118">특정 `COR_GC_REFERENCE` 값은 다음과 같은 종류의 관리되는 개체를 반영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="1bc08-119">관리되는 모든 스택()의`CorGCReferenceType.CorReferenceStack`개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="1bc08-120">여기에는 관리 코드의 라이브 참조와 공통 언어 런타임에 의해 생성된 개체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="1bc08-121">핸들 테이블 ()의`CorGCReferenceType.CorHandle*`개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="1bc08-122">여기에는 모듈의`HNDTYPE_STRONG` `HNDTYPE_REFCOUNT`강력한 참조(및) 및 정적 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="1bc08-123">종료자 큐()의`CorGCReferenceType.CorReferenceFinalizer`개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="1bc08-124">종료자 큐는 종료자가 실행될 때까지 개체를 루트합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="1bc08-125">필드에는 `extraData` 참조의 원본(또는 형식)에 따라 추가 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="1bc08-126">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-126">Possible values are:</span></span>  
  
- <span data-ttu-id="1bc08-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="1bc08-127">`DependentSource`.</span></span> <span data-ttu-id="1bc08-128">이 `type` `CorGCREferenceType.CorHandleStrongDependent`필드는 이 필드가 있는 경우 `COR_GC_REFERENCE.Location`에서 가비지 수집할 개체를 뿌리로 지정하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="1bc08-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="1bc08-129">`RefCount`.</span></span> <span data-ttu-id="1bc08-130">의 `type` `CorGCREferenceType.CorHandleStrongRefCount`경우 이 필드는 핸들의 참조 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="1bc08-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="1bc08-131">`Size`.</span></span> <span data-ttu-id="1bc08-132">이 `type` `CorGCREferenceType.CorHandleStrongSizedByref`경우 이 필드는 가비지 수집기에서 개체 루트를 계산한 개체 트리의 마지막 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="1bc08-133">이 계산이 반드시 최신 날짜는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1bc08-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bc08-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1bc08-134">Requirements</span></span>  
 <span data-ttu-id="1bc08-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc08-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bc08-136">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bc08-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bc08-137">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bc08-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bc08-138">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bc08-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bc08-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bc08-139">See also</span></span>

- [<span data-ttu-id="1bc08-140">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="1bc08-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="1bc08-141">디버깅</span><span class="sxs-lookup"><span data-stu-id="1bc08-141">Debugging</span></span>](index.md)
