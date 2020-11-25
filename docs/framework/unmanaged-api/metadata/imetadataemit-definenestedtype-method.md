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
ms.openlocfilehash: 99dc141cca0f911c8dd65645f6c22d950cc678d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719543"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="4757d-102">IMetaDataEmit::DefineNestedType 메서드</span><span class="sxs-lookup"><span data-stu-id="4757d-102">IMetaDataEmit::DefineNestedType Method</span></span>

<span data-ttu-id="4757d-103">형식 정의의 메타 데이터 서명을 만들고, `mdTypeDef` 해당 형식에 대 한 토큰을 반환 하 고, 정의 된 형식이 매개 변수에서 참조 하는 형식의 멤버 임을 지정 합니다 `tdEncloser` .</span><span class="sxs-lookup"><span data-stu-id="4757d-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4757d-104">구문</span><span class="sxs-lookup"><span data-stu-id="4757d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4757d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4757d-105">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="4757d-106">진행 유니코드 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4757d-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="4757d-107">[in] `TypeDef` 특성.</span><span class="sxs-lookup"><span data-stu-id="4757d-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="4757d-108">값의 비트 마스크입니다 `CorTypeAttr` .</span><span class="sxs-lookup"><span data-stu-id="4757d-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="4757d-109">진행 기본 클래스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4757d-109">[in] The token of the base class.</span></span> <span data-ttu-id="4757d-110">`mdTypeDef`또는 `mdTypeRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4757d-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="4757d-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="4757d-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="4757d-112">진행 이 클래스 또는 인터페이스가 구현 하는 인터페이스를 지정 하는 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4757d-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="4757d-113">진행 바깥쪽 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4757d-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="4757d-114">배열의 마지막 요소는 이어야 합니다 `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="4757d-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="4757d-115">제한이 `mdTypeDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4757d-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4757d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4757d-116">Requirements</span></span>  

 <span data-ttu-id="4757d-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4757d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4757d-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4757d-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4757d-119">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4757d-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4757d-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4757d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4757d-121">참조</span><span class="sxs-lookup"><span data-stu-id="4757d-121">See also</span></span>

- [<span data-ttu-id="4757d-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4757d-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4757d-123">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4757d-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
