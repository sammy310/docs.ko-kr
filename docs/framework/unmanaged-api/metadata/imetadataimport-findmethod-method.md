---
title: IMetaDataImport::FindMethod 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4225794740b7786c6f758c9a0953d323c31a1081
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782484"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="bb2ed-102">IMetaDataImport::FindMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="bb2ed-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="bb2ed-103">토큰을 가져옵니다 methoddef 묶여 있는 메서드에 대 한 지정 된 <xref:System.Type> 지정 된 이름 및 메타 데이터 서명을 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb2ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="bb2ed-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb2ed-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bb2ed-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bb2ed-106">[in] `mdTypeDef` 검색할 멤버를 포함 하는 형식 (클래스 또는 인터페이스)에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="bb2ed-107">이 값이 `mdTokenNil`, 다음 전역 함수에 대 한 조회가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="bb2ed-108">[in] 검색할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="bb2ed-109">[in] 메서드 서명의 이진 메타 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="bb2ed-110">[in] 크기 (바이트) `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="bb2ed-111">[out] 일치 하는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb2ed-112">설명</span><span class="sxs-lookup"><span data-stu-id="bb2ed-112">Remarks</span></span>  
 <span data-ttu-id="bb2ed-113">바깥쪽 클래스 또는 인터페이스를 사용 하는 메서드를 지정 (`td`), 해당 이름 (`szName`), 및 해당 서명 필요에 따라 (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="bb2ed-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="bb2ed-114">클래스 또는 인터페이스에서 동일한 이름 가진 여러 메서드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="bb2ed-115">이 경우 고유한 일치 항목을 찾을 메서드 시그니처를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="bb2ed-116">에 전달 된 서명을 `FindMethod` 시그니처는 특정 범위에 바인딩되므로 현재 범위에서 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="bb2ed-117">시그니처는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="bb2ed-118">토큰은 로컬 TypeDef 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="bb2ed-119">현재 범위의 컨텍스트 외부 런타임 시그니처를 만들어 없으며를 사용 하 여 해당 서명을 입력으로 `FindMethod`입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="bb2ed-120">`FindMethod` 클래스 또는 인터페이스에서 직접 정의 된 메서드를만 찾습니다. 상속 된 메서드를 찾지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb2ed-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb2ed-121">Requirements</span></span>  
 <span data-ttu-id="bb2ed-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bb2ed-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb2ed-123">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb2ed-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb2ed-124">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="bb2ed-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb2ed-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb2ed-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2ed-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="bb2ed-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="bb2ed-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb2ed-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bb2ed-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb2ed-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
