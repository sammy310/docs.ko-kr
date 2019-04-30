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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 277e7e57ae01128039c3a280158110acde3363a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944549"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="16c4f-102">IMetaDataEmit::MergeEnd 메서드</span><span class="sxs-lookup"><span data-stu-id="16c4f-102">IMetaDataEmit::MergeEnd Method</span></span>
<span data-ttu-id="16c4f-103">병합 현재 범위에 하나 이상의 이전 호출에 의해 지정 된 모든 메타 데이터 범위가 [imetadataemit:: 병합](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16c4f-104">구문</span><span class="sxs-lookup"><span data-stu-id="16c4f-104">Syntax</span></span>  
  
```  
HRESULT MergeEnd ();  
```  
  
## <a name="parameters"></a><span data-ttu-id="16c4f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16c4f-105">Parameters</span></span>  
 <span data-ttu-id="16c4f-106">이 메서드는 매개 변수 없이 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-106">This method takes no parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16c4f-107">설명</span><span class="sxs-lookup"><span data-stu-id="16c4f-107">Remarks</span></span>  
 <span data-ttu-id="16c4f-108">이 루틴은 메타 데이터의 실제 병합 트리거, 모든 가져오기에 대 한 호출 앞에서 지정한 범위 `IMetaDataEmit::Merge`, 현재 출력 범위로 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>  
  
 <span data-ttu-id="16c4f-109">다음과 같은 특수 병합에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-109">The following special conditions apply to the merge:</span></span>  
  
- <span data-ttu-id="16c4f-110">메타 데이터 가져오기 범위에 고유 하기 때문에 모듈 버전 식별자 (MVID) 되지 가져오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>  
  
- <span data-ttu-id="16c4f-111">없는 기존 모듈 수준의 속성을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-111">No existing module-wide properties are overwritten.</span></span>  
  
     <span data-ttu-id="16c4f-112">현재 범위에 대 한 모듈 속성이 이미 설정 된 경우 모듈 속성이 없는 가져와집니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="16c4f-113">그러나 현재 범위의 모듈 속성을 설정 하지 않은 경우 가져온 처음 발생할 때 한 번만 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="16c4f-114">이러한 모듈 속성 다시 발생 하는 경우 중복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="16c4f-115">(MVID)를 제외한 모든 모듈 속성의 값이 비교 됩니다. 중복 되 고 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>  
  
- <span data-ttu-id="16c4f-116">형식 정의 (`TypeDef`), 현재 범위에 중복 항목이 없으면 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="16c4f-117">`TypeDef` 개체를 각각에 대해 중복 검사 *정규화 된 개체 이름* + *GUID* + *버전 번호*합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="16c4f-118">이름 또는 GUID에서 일치 하는 경우 다른 두 요소 중 하나라도 다른 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="16c4f-119">그렇지 않으면 일치 하는 모든 세 항목이 `MergeEnd` 는 항목은 실제로 중복 항목이 되도록 대략적인 검사를 그렇지 않은 경우 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="16c4f-120">대략적인이 검사를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-120">This cursory check looks for:</span></span>  
  
    - <span data-ttu-id="16c4f-121">동일한 멤버 선언 같은 순서로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="16c4f-122">으로 플래그가 지정 되는 멤버 `mdPrivateScope` (참조를 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형)이이 확인은 특수 병합 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>  
  
    - <span data-ttu-id="16c4f-123">동일한 클래스 레이아웃입니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-123">The same class layout.</span></span>  
  
     <span data-ttu-id="16c4f-124">즉, 한 `TypeDef` 개체 항상 완벽 하 게 하 고 일관 되 게에서 정의 해야 모든 메타 데이터 범위는 선언 된; 전체 정의로 간주 됩니다 (클래스)에 대 한 해당 멤버 구현을 여러 컴파일 단위에 분산 되어, 하는 경우 모든 범위에 증분이 아닌 각 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="16c4f-125">예를 들어, 매개 변수 이름을 계약 관련 된 경우 내보내야 동일한 방식으로 모든 범위로; 관련 없는 경우는 내보내지 않아야 메타 데이터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>  
  
     <span data-ttu-id="16c4f-126">예외를 `TypeDef` 로 플래그가 지정 된 증분 멤버 개체에 있을 수 `mdPrivateScope`입니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="16c4f-127">이러한 발생 했을 때 `MergeEnd` 증분 방식으로 중복 항목에 관계 없이 현재 범위에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="16c4f-128">전용 범위를 인식 하기 때문에 컴파일러는 규칙을 적용 하는 일을 담당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>  
  
- <span data-ttu-id="16c4f-129">가상 Rva (상대 주소)는 가져오거나 병합; 컴파일러는이 정보를 다시 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>  
  
- <span data-ttu-id="16c4f-130">연결 된 항목을 병합 하는 경우에 사용자 지정 특성이 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="16c4f-131">예를 들어, 클래스와 연관 된 사용자 지정 특성 클래스 처음 발생 하는 경우 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="16c4f-132">사용자 지정 특성이 연결 된 경우는 `TypeDef` 또는 `MemberDef` 입니다 (예: 멤버 컴파일 타임 스탬프) 컴파일 단위, 병합 되지 않습니다 및 컴파일러에서 제거 하거나 이러한 메타 데이터를 업데이트 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="16c4f-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16c4f-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16c4f-133">Requirements</span></span>  
 <span data-ttu-id="16c4f-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="16c4f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16c4f-135">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="16c4f-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="16c4f-136">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="16c4f-136">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16c4f-137">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16c4f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c4f-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="16c4f-138">See also</span></span>

- [<span data-ttu-id="16c4f-139">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16c4f-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="16c4f-140">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16c4f-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
