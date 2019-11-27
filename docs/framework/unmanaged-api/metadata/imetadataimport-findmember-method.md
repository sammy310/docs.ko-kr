---
title: IMetaDataImport::FindMember 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: 7a46fa5319a1badc0cf28dcdbf535a6ed017c9c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437922"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="323d2-102">IMetaDataImport::FindMember 메서드</span><span class="sxs-lookup"><span data-stu-id="323d2-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="323d2-103">지정 된 <xref:System.Type>로 묶고 지정 된 이름과 메타 데이터 시그니처를 가진 필드 또는 메서드에 대 한 MemberDef 토큰에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="323d2-104">구문</span><span class="sxs-lookup"><span data-stu-id="323d2-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="323d2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="323d2-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="323d2-106">진행 검색할 멤버를 둘러싸는 클래스 또는 인터페이스의 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="323d2-107">이 값이 `mdTokenNil`되 면 전역 변수나 전역 함수에 대 한 조회가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="323d2-108">진행 검색할 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="323d2-109">진행 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="323d2-110">진행 `pvSigBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="323d2-111">제한이 일치 하는 MemberDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="323d2-112">주의</span><span class="sxs-lookup"><span data-stu-id="323d2-112">Remarks</span></span>  
 <span data-ttu-id="323d2-113">바깥쪽 클래스 또는 인터페이스 (`td`), 이름 (`szName`) 및 선택적으로 시그니처 (`pvSigBlob`)를 사용 하 여 멤버를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="323d2-114">클래스 또는 인터페이스에 이름이 같은 멤버가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="323d2-115">이 경우 멤버의 시그니처를 전달 하 여 고유한 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="323d2-116">서명이 특정 범위에 바인딩되므로 현재 범위에서 `FindMember` 전달 된 서명이 생성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="323d2-117">시그니처에는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="323d2-118">토큰은 로컬 TypeDef 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="323d2-119">현재 범위의 컨텍스트 외부에서 런타임 시그니처를 작성 하 고 해당 서명을 `FindMember`입력의 입력으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="323d2-120">`FindMember`은 클래스 또는 인터페이스에서 직접 정의 된 멤버만 찾습니다. 상속 된 멤버를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="323d2-121">`FindMember`은 도우미 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="323d2-122">[IMetaDataImport:: FindMethod;를](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md)호출 합니다. 이 호출에서 일치 하는 항목을 찾지 못하면 `FindMember` [IMetaDataImport:: FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="323d2-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="323d2-123">Requirements</span></span>  
 <span data-ttu-id="323d2-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="323d2-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="323d2-125">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="323d2-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="323d2-126">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="323d2-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="323d2-127">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="323d2-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="323d2-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="323d2-128">See also</span></span>

- [<span data-ttu-id="323d2-129">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="323d2-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="323d2-130">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="323d2-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
