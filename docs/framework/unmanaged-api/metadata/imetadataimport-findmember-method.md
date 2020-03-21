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
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177278"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="4d4ce-102">IMetaDataImport::FindMember 메서드</span><span class="sxs-lookup"><span data-stu-id="4d4ce-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="4d4ce-103">지정된 <xref:System.Type> 이름과 메타데이터 서명이 있는 필드 또는 메서드에 대한 MemberDef 토큰에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d4ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="4d4ce-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d4ce-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4d4ce-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="4d4ce-106">【인】 검색할 멤버를 둘러싸는 클래스 또는 인터페이스에 대한 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="4d4ce-107">이 값이 `mdTokenNil`이경우 전역 변수 또는 전역 함수에 대해 조회가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="4d4ce-108">【인】 검색할 구성원의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="4d4ce-109">【인】 멤버의 이진 메타데이터 시그니처에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="4d4ce-110">【인】 의 바이트 크기입니다. `pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="4d4ce-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="4d4ce-111">【아웃】 일치하는 MemberDef 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d4ce-112">설명</span><span class="sxs-lookup"><span data-stu-id="4d4ce-112">Remarks</span></span>  
 <span data-ttu-id="4d4ce-113">enclosing 클래스 또는 인터페이스 (),`td`해당 이름`szName`() 및 선택적으로`pvSigBlob`해당 서명 ()을 사용 하 여 멤버를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="4d4ce-114">클래스 또는 인터페이스에 이름이 같은 구성원이 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="4d4ce-115">이 경우 멤버의 서명을 전달하여 고유한 일치 를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="4d4ce-116">전달된 서명은 서명이 특정 범위에 바인딩되어 있으므로 현재 범위에서 생성되어야 `FindMember` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="4d4ce-117">서명은 둘러싸는 클래스 또는 값 형식을 식별하는 토큰을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="4d4ce-118">토큰은 로컬 TypeDef 테이블에 대한 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="4d4ce-119">현재 범위의 컨텍스트 외부에서 런타임 서명을 빌드하고 해당 서명을 `FindMember`에 입력에 대한 입력으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="4d4ce-120">`FindMember`클래스 또는 인터페이스에서 직접 정의된 멤버만 찾습니다. 상속된 멤버를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d4ce-121">`FindMember`은 도우미 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="4d4ce-122">[IMetaDataImport를 호출합니다::FindMethod;](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md) 해당 호출이 일치하는 `FindMember` 호출을 찾지 못하면 [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d4ce-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d4ce-123">Requirements</span></span>  
 <span data-ttu-id="4d4ce-124">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d4ce-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d4ce-125">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="4d4ce-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d4ce-126">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4d4ce-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4d4ce-127">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d4ce-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d4ce-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d4ce-128">See also</span></span>

- [<span data-ttu-id="4d4ce-129">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d4ce-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4d4ce-130">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d4ce-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
