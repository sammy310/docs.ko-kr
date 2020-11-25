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
ms.openlocfilehash: 111e42a6d8f413c616779bc44e0722ab38781588
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711340"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="8363d-102">IMetaDataImport::FindMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="8363d-102">IMetaDataImport::FindMethod Method</span></span>

<span data-ttu-id="8363d-103">지정 된로 묶여 <xref:System.Type> 있고 지정 된 이름과 메타 데이터 시그니처가 있는 메서드의 MethodDef 토큰에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8363d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8363d-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8363d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8363d-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="8363d-106">진행 `mdTypeDef` 검색할 멤버를 둘러싸는 형식 (클래스 또는 인터페이스)에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="8363d-107">이 값이 이면 `mdTokenNil` 전역 함수에 대 한 조회가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="8363d-108">진행 검색할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="8363d-109">진행 메서드의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="8363d-110">진행 의 크기 (바이트) `pvSigBlob` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="8363d-111">제한이 일치 하는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8363d-112">설명</span><span class="sxs-lookup"><span data-stu-id="8363d-112">Remarks</span></span>  

 <span data-ttu-id="8363d-113">바깥쪽 클래스 또는 인터페이스 ( `td` ), 이름 ( `szName` ) 및 선택적으로 시그니처 ()를 사용 하 여 메서드를 지정 `pvSigBlob` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="8363d-114">클래스 또는 인터페이스에 동일한 이름을 가진 메서드가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="8363d-115">이 경우 메서드의 시그니처를 전달 하 여 고유한 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="8363d-116">서명이 특정 범위에 바인딩되기 때문에에 전달 된 시그니처는 `FindMethod` 현재 범위에서 생성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="8363d-117">시그니처에는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="8363d-118">토큰은 로컬 TypeDef 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="8363d-119">현재 범위의 컨텍스트 외부에서 런타임 서명을 작성 하 고 해당 시그니처를 입력을 위한 입력으로 사용할 수 없습니다 `FindMethod` .</span><span class="sxs-lookup"><span data-stu-id="8363d-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="8363d-120">`FindMethod` 클래스 또는 인터페이스에서 직접 정의 된 메서드만 찾습니다. 상속 된 메서드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8363d-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8363d-121">Requirements</span></span>  

 <span data-ttu-id="8363d-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8363d-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8363d-123">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8363d-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8363d-124">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8363d-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8363d-125">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8363d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8363d-126">참조</span><span class="sxs-lookup"><span data-stu-id="8363d-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="8363d-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8363d-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8363d-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8363d-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
