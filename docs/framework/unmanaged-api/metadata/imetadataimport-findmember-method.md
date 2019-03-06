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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 777d7bf51db3e6984f30e31c46ac115301d13faf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478975"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="dfb78-102">IMetaDataImport::FindMember 메서드</span><span class="sxs-lookup"><span data-stu-id="dfb78-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="dfb78-103">토큰을 가져옵니다 memberdef 묶여 있는 메서드나 필드에 대 한 지정 된 <xref:System.Type> 지정 된 이름 및 메타 데이터 서명을 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb78-104">구문</span><span class="sxs-lookup"><span data-stu-id="dfb78-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfb78-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dfb78-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="dfb78-106">[in] 검색할 멤버를 포함 하는 인터페이스를 클래스에 대 한 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="dfb78-107">이 값이 `mdTokenNil`, 전역 변수 또는 전역 함수에 대 한 조회가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="dfb78-108">[in] 검색할 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="dfb78-109">[in] 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="dfb78-110">[in] 크기 (바이트) `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="dfb78-111">[out] 일치 하는 MemberDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfb78-112">설명</span><span class="sxs-lookup"><span data-stu-id="dfb78-112">Remarks</span></span>  
 <span data-ttu-id="dfb78-113">바깥쪽 클래스 또는 인터페이스를 사용 하 여 멤버를 지정할 수 (`td`), 해당 이름 (`szName`), 및 해당 서명 필요에 따라 (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="dfb78-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="dfb78-114">클래스 또는 인터페이스에 이름이 같은 여러 멤버가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="dfb78-115">이 경우 고유한 일치 항목을 찾을 멤버의 시그니처를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="dfb78-116">에 전달 된 서명을 `FindMember` 시그니처는 특정 범위에 바인딩되므로 현재 범위에서 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="dfb78-117">시그니처는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="dfb78-118">토큰은 로컬 TypeDef 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="dfb78-119">현재 범위의 컨텍스트 외부 런타임 시그니처를 만들어 없으며를 사용 하 여 해당 서명을 입력으로 `FindMember`입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="dfb78-120">`FindMember` 클래스 또는 인터페이스에서 직접 정의 된 멤버를 찾습니다. 상속 된 멤버는 찾지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfb78-121">`FindMember` 도우미 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="dfb78-122">호출한 [imetadataimport:: Findmethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); 호출 하는 일치 하는 항목을 찾지 못하면 `FindMember` 호출 [imetadataimport:: Findfield](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb78-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfb78-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dfb78-123">Requirements</span></span>  
 <span data-ttu-id="dfb78-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dfb78-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfb78-125">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dfb78-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dfb78-126">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="dfb78-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dfb78-127">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfb78-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb78-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="dfb78-128">See also</span></span>
- [<span data-ttu-id="dfb78-129">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfb78-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dfb78-130">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfb78-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
