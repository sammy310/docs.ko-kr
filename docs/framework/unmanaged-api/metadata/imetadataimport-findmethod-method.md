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
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177259"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="aab65-102">IMetaDataImport::FindMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="aab65-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="aab65-103">지정된 <xref:System.Type> 이름과 메타데이터 서명이 있는 메서드에 대한 MethodDef 토큰에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aab65-104">구문</span><span class="sxs-lookup"><span data-stu-id="aab65-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aab65-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aab65-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="aab65-106">【인】 검색할 멤버를 둘러싸는 형식(클래스 또는 인터페이스)에 대한 `mdTypeDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="aab65-107">이 값이 `mdTokenNil`있으면 전역 함수에 대해 조회가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="aab65-108">【인】 검색할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="aab65-109">【인】 메서드의 이진 메타데이터 시그니처에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="aab65-110">【인】 의 바이트 크기입니다. `pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="aab65-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="aab65-111">【아웃】 일치하는 MethodDef 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aab65-112">설명</span><span class="sxs-lookup"><span data-stu-id="aab65-112">Remarks</span></span>  
 <span data-ttu-id="aab65-113">해당 둘러싸는 클래스 또는 인터페이스`td`(), 해당`szName`이름 () 및`pvSigBlob`선택적으로 해당 서명 ()을 사용 하 여 메서드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="aab65-114">클래스 또는 인터페이스에 이름이 같은 메서드가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="aab65-115">이 경우 메서드의 서명을 전달하여 고유한 일치 를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="aab65-116">전달된 서명은 서명이 특정 범위에 바인딩되어 있으므로 현재 범위에서 생성되어야 `FindMethod` 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="aab65-117">서명은 둘러싸는 클래스 또는 값 형식을 식별하는 토큰을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="aab65-118">토큰은 로컬 TypeDef 테이블에 대한 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="aab65-119">현재 범위의 컨텍스트 외부에서 런타임 서명을 빌드하고 해당 서명을 `FindMethod`에 입력에 대한 입력으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="aab65-120">`FindMethod`클래스 또는 인터페이스에서 직접 정의된 메서드만 찾습니다. 상속된 메서드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab65-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aab65-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aab65-121">Requirements</span></span>  
 <span data-ttu-id="aab65-122">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab65-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aab65-123">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="aab65-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aab65-124">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="aab65-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aab65-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aab65-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab65-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aab65-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="aab65-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aab65-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="aab65-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aab65-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
