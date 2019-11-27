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
ms.openlocfilehash: 470b6511366cef1680eaf97f9ab376736add55c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437889"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="699c7-102">IMetaDataImport::FindMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="699c7-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="699c7-103">지정 된 <xref:System.Type>로 묶고 지정 된 이름과 메타 데이터 서명을 가진 메서드에 대 한 MethodDef 토큰에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="699c7-104">구문</span><span class="sxs-lookup"><span data-stu-id="699c7-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="699c7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="699c7-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="699c7-106">진행 검색할 멤버를 둘러싸는 형식 (클래스 또는 인터페이스)에 대 한 `mdTypeDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="699c7-107">이 값이 `mdTokenNil`되 면 전역 함수에 대 한 조회가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="699c7-108">진행 검색할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="699c7-109">진행 메서드의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="699c7-110">진행 `pvSigBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="699c7-111">제한이 일치 하는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="699c7-112">설명</span><span class="sxs-lookup"><span data-stu-id="699c7-112">Remarks</span></span>  
 <span data-ttu-id="699c7-113">바깥쪽 클래스 또는 인터페이스 (`td`), 이름 (`szName`) 및 선택적으로 시그니처 (`pvSigBlob`)를 사용 하 여 메서드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="699c7-114">클래스 또는 인터페이스에 동일한 이름을 가진 메서드가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="699c7-115">이 경우 메서드의 시그니처를 전달 하 여 고유한 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="699c7-116">서명이 특정 범위에 바인딩되므로 현재 범위에서 `FindMethod` 전달 된 서명이 생성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="699c7-117">시그니처에는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="699c7-118">토큰은 로컬 TypeDef 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="699c7-119">현재 범위의 컨텍스트 외부에서 런타임 시그니처를 작성 하 고 해당 서명을 `FindMethod`입력의 입력으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="699c7-120">`FindMethod`은 클래스 또는 인터페이스에서 직접 정의 된 메서드만 찾습니다. 상속 된 메서드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="699c7-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="699c7-121">Requirements</span></span>  
 <span data-ttu-id="699c7-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="699c7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="699c7-123">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="699c7-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="699c7-124">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="699c7-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="699c7-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="699c7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699c7-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="699c7-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="699c7-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="699c7-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="699c7-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="699c7-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
