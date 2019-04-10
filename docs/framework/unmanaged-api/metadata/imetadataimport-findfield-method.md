---
title: IMetaDataImport::FindField 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 88cd08b4290739808079bc8ecb713a5c5ea96584
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172564"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="b7bab-102">IMetaDataImport::FindField 메서드</span><span class="sxs-lookup"><span data-stu-id="b7bab-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="b7bab-103">에 포인터를 가져옵니다 FieldDef 토큰 포함 되는 필드에 대 한 지정 된 <xref:System.Type> 지정 된 이름 및 메타 데이터 서명을 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7bab-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7bab-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7bab-104">Syntax</span></span>  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7bab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7bab-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b7bab-106">[in] 클래스 또는 검색할 필드를 포함 하는 인터페이스에 대 한 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b7bab-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="b7bab-107">이 값이 `mdTokenNil`, 전역 변수에 대 한 조회가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7bab-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="b7bab-108">[in] 검색할 필드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b7bab-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="b7bab-109">[in] 필드의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b7bab-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="b7bab-110">[in] 크기 (바이트) `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bab-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="b7bab-111">[out] 일치 하는 FieldDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b7bab-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7bab-112">설명</span><span class="sxs-lookup"><span data-stu-id="b7bab-112">Remarks</span></span>  
 <span data-ttu-id="b7bab-113">바깥쪽 클래스 또는 인터페이스를 사용 하 여 필드를 지정 했습니다 (`td`), 해당 이름 (`szName`), 및 해당 서명 필요에 따라 (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="b7bab-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="b7bab-114">에 전달 된 서명을 `FindField` 시그니처는 특정 범위에 바인딩되므로 현재 범위에서 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bab-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="b7bab-115">시그니처는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7bab-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="b7bab-116">(토큰은 로컬 TypeDef 테이블에 인덱스).</span><span class="sxs-lookup"><span data-stu-id="b7bab-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="b7bab-117">현재 범위의 컨텍스트 외부 런타임 시그니처를 한에 대 한 입력으로 사용할 수는 없습니다 `FindField`합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bab-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 `FindField` <span data-ttu-id="b7bab-118">클래스 또는 인터페이스에서 직접 정의 된 필드만을 찾습니다. 상속 된 필드는 찾지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7bab-118">finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7bab-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7bab-119">Requirements</span></span>  
 <span data-ttu-id="b7bab-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7bab-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7bab-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b7bab-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7bab-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b7bab-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b7bab-123">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b7bab-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7bab-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7bab-124">See also</span></span>

- [<span data-ttu-id="b7bab-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7bab-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b7bab-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7bab-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
