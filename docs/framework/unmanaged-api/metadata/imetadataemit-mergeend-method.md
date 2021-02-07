---
description: '자세히 알아보기: IMetaDataEmit:: MergeEnd 메서드'
title: IMetaDataEmit::MergeEnd 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
ms.openlocfilehash: aac48b9bafb60cee4e3d73232d9f9c00cca7f796
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745881"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="b76ab-103">IMetaDataEmit::MergeEnd 메서드</span><span class="sxs-lookup"><span data-stu-id="b76ab-103">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="b76ab-104">[IMetaDataEmit:: Merge](imetadataemit-merge-method.md)에 대 한 하나 이상의 이전 호출로 지정 된 모든 메타 데이터 범위를 현재 범위에 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-104">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="b76ab-105">구문</span><span class="sxs-lookup"><span data-stu-id="b76ab-105">Syntax</span></span>

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="b76ab-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b76ab-106">Parameters</span></span>

<span data-ttu-id="b76ab-107">이 메서드는 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-107">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="b76ab-108">설명</span><span class="sxs-lookup"><span data-stu-id="b76ab-108">Remarks</span></span>

<span data-ttu-id="b76ab-109">이 루틴은에 대 한 이전 호출로 지정 된 모든 가져오기 범위의 메타 데이터에 대 한 실제 병합을 `IMetaDataEmit::Merge` 현재 출력 범위로 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-109">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="b76ab-110">병합에는 다음과 같은 특수 조건이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-110">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="b76ab-111">모듈 버전 식별자 (MVID)는 가져오기 범위에서 메타 데이터에 고유 하기 때문에 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-111">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="b76ab-112">기존 모듈 차원의 속성은 덮어쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-112">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="b76ab-113">현재 범위에 대해 모듈 속성이 이미 설정 된 경우 모듈 속성을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-113">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="b76ab-114">그러나 현재 범위에서 모듈 속성을 설정 하지 않은 경우에는 처음 발견 될 때 한 번만 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-114">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="b76ab-115">이러한 모듈 속성이 다시 발생 하면 중복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-115">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="b76ab-116">모든 모듈 속성의 값 (MVID 제외)을 비교 하 고 중복 항목을 찾을 수 없는 경우 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-116">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="b76ab-117">형식 정의 ()의 경우에는 `TypeDef` 중복 항목이 현재 범위에 병합 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-117">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="b76ab-118">`TypeDef`개체는 정규화 된 각 *개체 이름*  +  *GUID*  +  *버전 번호* 에 대해 중복 항목을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-118">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="b76ab-119">이름 또는 GUID에 일치 하는 항목이 있고 다른 두 요소 중 하나가 다르면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-119">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="b76ab-120">그렇지 않고 세 항목 모두 일치 하는 경우 `MergeEnd` 항목이 실제로 중복 되는지 확인 하기 위해 간단한 검사를 수행 합니다. 그렇지 않으면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-120">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="b76ab-121">이 간단한 검사는 다음을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-121">This cursory check looks for:</span></span>

  - <span data-ttu-id="b76ab-122">동일한 멤버 선언이 동일한 순서로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-122">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="b76ab-123">`mdPrivateScope`( [CorMethodAttr](cormethodattr-enumeration.md) 열거형 참조)로 플래그가 지정 된 멤버는이 검사에 포함 되지 않으며 특수 하 게 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-123">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="b76ab-124">동일한 클래스 레이아웃입니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-124">The same class layout.</span></span>

  <span data-ttu-id="b76ab-125">즉 `TypeDef` , 개체가 선언 된 모든 메타 데이터 범위에서 항상 완전히 일관 되 게 정의 되어야 합니다. 클래스의 멤버 구현이 여러 컴파일 단위에 분산 된 경우 전체 정의는 모든 범위에 표시 되 고 각 범위에는 증분 되지 않는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-125">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="b76ab-126">예를 들어 매개 변수 이름이 계약과 관련 된 경우 모든 범위에서 동일한 방식으로 내보내야 합니다. 관련이 없는 경우 메타 데이터로 내보내지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-126">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="b76ab-127">단, 개체에는 `TypeDef` 로 플래그가 지정 된 증분 멤버가 있을 수 있습니다 `mdPrivateScope` .</span><span class="sxs-lookup"><span data-stu-id="b76ab-127">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="b76ab-128">이러한 항목이 발견 되 면 `MergeEnd` 중복을 고려 하지 않고 현재 범위에 증분 방식으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-128">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="b76ab-129">컴파일러는 전용 범위를 이해 하므로 컴파일러는 규칙 적용을 담당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-129">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="b76ab-130">Rva (상대 가상 주소)는 가져오거나 병합 되지 않습니다. 컴파일러는이 정보를 다시 내보낼 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-130">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="b76ab-131">사용자 지정 특성은 해당 특성이 첨부 된 항목이 병합 될 때만 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-131">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="b76ab-132">예를 들어 클래스와 연결 된 사용자 지정 특성은 클래스를 처음 발견할 때 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-132">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="b76ab-133">사용자 지정 특성이 `TypeDef` `MemberDef` 컴파일 단위 (예: 멤버 컴파일의 타임 스탬프)와 관련 된 또는와 연결 된 경우에는 병합 되지 않으며 컴파일러에서 해당 메타 데이터를 제거 하거나 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-133">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="b76ab-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b76ab-134">Requirements</span></span>

<span data-ttu-id="b76ab-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b76ab-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b76ab-136">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b76ab-136">**Header:** Cor.h</span></span>

<span data-ttu-id="b76ab-137">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b76ab-137">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="b76ab-138">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b76ab-138">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b76ab-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b76ab-139">See also</span></span>

- [<span data-ttu-id="b76ab-140">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b76ab-140">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b76ab-141">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b76ab-141">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
