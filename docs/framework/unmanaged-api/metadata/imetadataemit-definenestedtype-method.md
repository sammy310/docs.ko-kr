---
description: IMetaDataEmit::D efineNestedType 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 1b0c5c8d1bffa425b2019a4434042c84a0069907
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753382"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="622d0-103">IMetaDataEmit::DefineNestedType 메서드</span><span class="sxs-lookup"><span data-stu-id="622d0-103">IMetaDataEmit::DefineNestedType Method</span></span>

<span data-ttu-id="622d0-104">형식 정의의 메타 데이터 서명을 만들고, `mdTypeDef` 해당 형식에 대 한 토큰을 반환 하 고, 정의 된 형식이 매개 변수에서 참조 하는 형식의 멤버 임을 지정 합니다 `tdEncloser` .</span><span class="sxs-lookup"><span data-stu-id="622d0-104">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="622d0-105">구문</span><span class="sxs-lookup"><span data-stu-id="622d0-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="622d0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="622d0-106">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="622d0-107">진행 유니코드 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="622d0-107">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="622d0-108">[in] `TypeDef` 특성.</span><span class="sxs-lookup"><span data-stu-id="622d0-108">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="622d0-109">값의 비트 마스크입니다 `CorTypeAttr` .</span><span class="sxs-lookup"><span data-stu-id="622d0-109">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="622d0-110">진행 기본 클래스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="622d0-110">[in] The token of the base class.</span></span> <span data-ttu-id="622d0-111">`mdTypeDef`또는 `mdTypeRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="622d0-111">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="622d0-112">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="622d0-112">`rtkImplements`[]</span></span>  
 <span data-ttu-id="622d0-113">진행 이 클래스 또는 인터페이스가 구현 하는 인터페이스를 지정 하는 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="622d0-113">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="622d0-114">진행 바깥쪽 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="622d0-114">[in] The token of the enclosing type.</span></span> <span data-ttu-id="622d0-115">배열의 마지막 요소는 이어야 합니다 `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="622d0-115">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="622d0-116">제한이 `mdTypeDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="622d0-116">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="622d0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="622d0-117">Requirements</span></span>  

 <span data-ttu-id="622d0-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="622d0-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="622d0-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="622d0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="622d0-120">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="622d0-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="622d0-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="622d0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="622d0-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="622d0-122">See also</span></span>

- [<span data-ttu-id="622d0-123">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="622d0-123">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="622d0-124">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="622d0-124">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
