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
ms.openlocfilehash: 9b42f0f7c8e2878ee3ec140344f51517a24247c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729865"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="f65f8-102">IMetaDataImport::FindField 메서드</span><span class="sxs-lookup"><span data-stu-id="f65f8-102">IMetaDataImport::FindField Method</span></span>

<span data-ttu-id="f65f8-103">지정 된로 묶고 <xref:System.Type> 지정 된 이름과 메타 데이터 시그니처가 있는 필드의 FieldDef 토큰에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f65f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="f65f8-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f65f8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f65f8-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="f65f8-106">진행 검색할 필드를 둘러싸는 클래스 또는 인터페이스의 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="f65f8-107">이 값이 이면 `mdTokenNil` 전역 변수에 대 한 조회가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="f65f8-108">진행 검색할 필드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f65f8-109">진행 필드의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f65f8-110">진행 의 크기 (바이트) `pvSigBlob` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="f65f8-111">제한이 일치 하는 FieldDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f65f8-112">설명</span><span class="sxs-lookup"><span data-stu-id="f65f8-112">Remarks</span></span>  

 <span data-ttu-id="f65f8-113">바깥쪽 클래스 또는 인터페이스 ( `td` ), 이름 ( `szName` ) 및 선택적으로 시그니처 ()를 사용 하 여 필드를 지정 `pvSigBlob` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="f65f8-114">서명이 특정 범위에 바인딩되기 때문에에 전달 된 시그니처는 `FindField` 현재 범위에서 생성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="f65f8-115">시그니처에는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="f65f8-116">토큰은 로컬 TypeDef 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="f65f8-117">현재 범위의 컨텍스트 외부에서 런타임 서명을 작성 하 고 해당 서명을에 대 한 입력으로 사용할 수 없습니다 `FindField` .</span><span class="sxs-lookup"><span data-stu-id="f65f8-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="f65f8-118">`FindField` 클래스 또는 인터페이스에서 직접 정의 된 필드만 찾습니다. 상속 된 필드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f65f8-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f65f8-119">Requirements</span></span>  

 <span data-ttu-id="f65f8-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f65f8-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f65f8-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f65f8-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f65f8-122">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f65f8-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f65f8-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f65f8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65f8-124">참조</span><span class="sxs-lookup"><span data-stu-id="f65f8-124">See also</span></span>

- [<span data-ttu-id="f65f8-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f65f8-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f65f8-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f65f8-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
