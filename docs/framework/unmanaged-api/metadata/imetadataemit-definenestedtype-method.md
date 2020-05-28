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
ms.openlocfilehash: 2b24c2ca6907dfdb63ad934ec30557c246db174c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004357"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="f5139-102">IMetaDataEmit::DefineNestedType 메서드</span><span class="sxs-lookup"><span data-stu-id="f5139-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="f5139-103">형식 정의의 메타 데이터 서명을 만들고, `mdTypeDef` 해당 형식에 대 한 토큰을 반환 하 고, 정의 된 형식이 매개 변수에서 참조 하는 형식의 멤버 임을 지정 합니다 `tdEncloser` .</span><span class="sxs-lookup"><span data-stu-id="f5139-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5139-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5139-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f5139-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5139-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="f5139-106">진행 유니코드 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f5139-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="f5139-107">[in] `TypeDef` 특성.</span><span class="sxs-lookup"><span data-stu-id="f5139-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="f5139-108">값의 비트 마스크입니다 `CorTypeAttr` .</span><span class="sxs-lookup"><span data-stu-id="f5139-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="f5139-109">진행 기본 클래스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f5139-109">[in] The token of the base class.</span></span> <span data-ttu-id="f5139-110">`mdTypeDef`또는 `mdTypeRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f5139-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="f5139-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="f5139-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="f5139-112">진행 이 클래스 또는 인터페이스가 구현 하는 인터페이스를 지정 하는 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f5139-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="f5139-113">진행 바깥쪽 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f5139-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="f5139-114">배열의 마지막 요소는 이어야 합니다 `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="f5139-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="f5139-115">제한이 `mdTypeDef`할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f5139-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5139-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5139-116">Requirements</span></span>  
 <span data-ttu-id="f5139-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5139-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5139-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f5139-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5139-119">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5139-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5139-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5139-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5139-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5139-121">See also</span></span>

- [<span data-ttu-id="f5139-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5139-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f5139-123">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5139-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
