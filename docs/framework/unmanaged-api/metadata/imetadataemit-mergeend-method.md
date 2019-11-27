---
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
ms.openlocfilehash: 34ecfc2f01f22971e135358806adeea632e02f8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448033"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="1d9be-102">IMetaDataEmit::MergeEnd 메서드</span><span class="sxs-lookup"><span data-stu-id="1d9be-102">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="1d9be-103">[IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)에 대 한 하나 이상의 이전 호출로 지정 된 모든 메타 데이터 범위를 현재 범위에 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="1d9be-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d9be-104">Syntax</span></span>

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="1d9be-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d9be-105">Parameters</span></span>

<span data-ttu-id="1d9be-106">이 메서드는 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-106">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d9be-107">주의</span><span class="sxs-lookup"><span data-stu-id="1d9be-107">Remarks</span></span>

<span data-ttu-id="1d9be-108">이 루틴은 `IMetaDataEmit::Merge`에 대 한 이전 호출로 지정 된 모든 가져오기 범위의 메타 데이터에 대 한 실제 병합을 현재 출력 범위로 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="1d9be-109">병합에는 다음과 같은 특수 조건이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-109">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="1d9be-110">모듈 버전 식별자 (MVID)는 가져오기 범위에서 메타 데이터에 고유 하기 때문에 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="1d9be-111">기존 모듈 차원의 속성은 덮어쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-111">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="1d9be-112">현재 범위에 대해 모듈 속성이 이미 설정 된 경우 모듈 속성을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="1d9be-113">그러나 현재 범위에서 모듈 속성을 설정 하지 않은 경우에는 처음 발견 될 때 한 번만 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="1d9be-114">이러한 모듈 속성이 다시 발생 하면 중복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="1d9be-115">모든 모듈 속성의 값 (MVID 제외)을 비교 하 고 중복 항목을 찾을 수 없는 경우 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="1d9be-116">형식 정의 (`TypeDef`)의 경우 중복 항목이 현재 범위에 병합 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="1d9be-117">`TypeDef` 개체는 정규화 된 각 *개체 이름* + *GUID* + *버전 번호*에 대해 중복 항목을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="1d9be-118">이름 또는 GUID에 일치 하는 항목이 있고 다른 두 요소 중 하나가 다르면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="1d9be-119">그렇지 않고 세 항목이 모두 `MergeEnd` 일치 하는 경우 간단한는 항목이 실제로 중복 되는지 확인 하는 검사를 수행 합니다. 그렇지 않으면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="1d9be-120">이 간단한 검사는 다음을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-120">This cursory check looks for:</span></span>

  - <span data-ttu-id="1d9be-121">동일한 멤버 선언이 동일한 순서로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="1d9be-122">`mdPrivateScope` ( [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형 참조)로 플래그가 지정 된 멤버는이 검사에 포함 되지 않습니다. 특수 하 게 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="1d9be-123">동일한 클래스 레이아웃입니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-123">The same class layout.</span></span>

  <span data-ttu-id="1d9be-124">즉, `TypeDef` 개체가 선언 된 모든 메타 데이터 범위에서 항상 완전히 일관 되 게 정의 되어야 합니다. 클래스에 대 한 멤버 구현이 여러 컴파일 단위에 걸쳐 분산 된 경우 전체 정의는 모든 범위에 표시 되 고 각 범위에는 증분 되지 않는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="1d9be-125">예를 들어 매개 변수 이름이 계약과 관련 된 경우 모든 범위에서 동일한 방식으로 내보내야 합니다. 관련이 없는 경우 메타 데이터로 내보내지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="1d9be-126">단, `TypeDef` 개체에는 `mdPrivateScope`으로 플래그가 지정 된 증분 멤버가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="1d9be-127">이러한 항목이 발견 되 면 중복을 고려 하지 않고 `MergeEnd`을 현재 범위에 증분 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="1d9be-128">컴파일러는 전용 범위를 이해 하므로 컴파일러는 규칙 적용을 담당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="1d9be-129">Rva (상대 가상 주소)는 가져오거나 병합 되지 않습니다. 컴파일러는이 정보를 다시 내보낼 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="1d9be-130">사용자 지정 특성은 해당 특성이 첨부 된 항목이 병합 될 때만 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="1d9be-131">예를 들어 클래스와 연결 된 사용자 지정 특성은 클래스를 처음 발견할 때 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="1d9be-132">사용자 지정 특성이 컴파일 단위에 해당 하는 `TypeDef` 또는 `MemberDef`와 연결 된 경우 (예: 멤버 컴파일의 타임 스탬프) 병합 되지 않으며 이러한 메타 데이터를 제거 하거나 업데이트 하는 것이 컴파일러에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="1d9be-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d9be-133">Requirements</span></span>

<span data-ttu-id="1d9be-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d9be-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="1d9be-135">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1d9be-135">**Header:** Cor.h</span></span>

<span data-ttu-id="1d9be-136">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9be-136">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="1d9be-137">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d9be-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1d9be-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d9be-138">See also</span></span>

- [<span data-ttu-id="1d9be-139">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d9be-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1d9be-140">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d9be-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
