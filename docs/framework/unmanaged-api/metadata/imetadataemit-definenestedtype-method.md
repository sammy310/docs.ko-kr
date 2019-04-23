---
title: IMetaDataEmit::DefineNestedType 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ebd4e9beca315ef8284c915800afec6bdb78c78
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183237"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="8d851-102">IMetaDataEmit::DefineNestedType 메서드</span><span class="sxs-lookup"><span data-stu-id="8d851-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="8d851-103">메타 데이터 서명의 형식 정의 만들고, 반환 합니다는 `mdTypeDef` 해당 형식에 대 한 토큰 및 형식 정의에서 참조 형식의 멤버를 지정 합니다 `tdEncloser` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8d851-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d851-104">구문</span><span class="sxs-lookup"><span data-stu-id="8d851-104">Syntax</span></span>  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d851-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8d851-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="8d851-106">[in] 유니코드 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8d851-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="8d851-107">[in] `TypeDef` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8d851-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="8d851-108">이 비트 마스크의 `CorTypeAttr` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d851-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="8d851-109">[in] 토큰의 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8d851-109">[in] The token of the base class.</span></span> <span data-ttu-id="8d851-110">이 값은 `mdTypeDef` 또는 `mdTypeRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8d851-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="8d851-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="8d851-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="8d851-112">[in] 이 클래스 또는 인터페이스를 구현 하는 인터페이스를 지정 하는 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="8d851-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="8d851-113">[in] 바깥쪽 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8d851-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="8d851-114">배열의 마지막 요소 여야 합니다 `mdTokenNil`합니다.</span><span class="sxs-lookup"><span data-stu-id="8d851-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="8d851-115">[out] `mdTypeDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8d851-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d851-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d851-116">Requirements</span></span>  
 <span data-ttu-id="8d851-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8d851-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d851-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8d851-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d851-119">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="8d851-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d851-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d851-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d851-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="8d851-121">See also</span></span>

- [<span data-ttu-id="8d851-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d851-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8d851-123">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d851-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
