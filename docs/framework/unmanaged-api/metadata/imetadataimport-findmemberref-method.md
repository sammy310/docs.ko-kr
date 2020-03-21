---
title: IMetaDataImport::FindMemberRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175423"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="ede01-102">IMetaDataImport::FindMemberRef 메서드</span><span class="sxs-lookup"><span data-stu-id="ede01-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="ede01-103">지정된 <xref:System.Type> 이름과 메타데이터 서명이 있는 멤버 참조에 대한 MemberRef 토큰에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ede01-104">구문</span><span class="sxs-lookup"><span data-stu-id="ede01-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ede01-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ede01-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ede01-106">【인】 검색할 멤버 참조를 둘러싸는 클래스 또는 인터페이스에 대한 TypeRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="ede01-107">이 값이 `mdTokenNil`이경우 전역 변수 또는 전역 함수 참조에 대해 조회가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="ede01-108">【인】 검색할 멤버 참조의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="ede01-109">【인】 멤버 참조의 이진 메타데이터 시그니처에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="ede01-110">【인】 의 바이트 크기입니다. `pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="ede01-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="ede01-111">【아웃】 일치하는 MemberRef 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ede01-112">설명</span><span class="sxs-lookup"><span data-stu-id="ede01-112">Remarks</span></span>  
 <span data-ttu-id="ede01-113">enclosing 클래스 또는 인터페이스 (),`td`해당 이름`szName`() 및 선택적으로`pvSigBlob`해당 서명 ()을 사용 하 여 멤버를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="ede01-114">전달된 서명은 서명이 특정 범위에 바인딩되어 있으므로 현재 범위에서 생성되어야 `FindMemberRef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="ede01-115">서명은 둘러싸는 클래스 또는 값 형식을 식별하는 토큰을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="ede01-116">토큰은 로컬 TypeDef 테이블에 대한 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="ede01-117">현재 범위의 컨텍스트 외부에서 런타임 서명을 작성하고 해당 서명을 `FindMemberRef`에 대한 입력으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="ede01-118">`FindMemberRef`클래스 또는 인터페이스에서 직접 정의된 멤버 참조만 찾습니다. 상속된 멤버 참조를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ede01-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ede01-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ede01-119">Requirements</span></span>  
 <span data-ttu-id="ede01-120">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ede01-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ede01-121">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="ede01-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ede01-122">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ede01-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ede01-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ede01-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede01-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ede01-124">See also</span></span>

- [<span data-ttu-id="ede01-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ede01-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ede01-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ede01-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
