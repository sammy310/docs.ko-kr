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
ms.openlocfilehash: 3b8fd9876563bace52a6088747d1ca4ed26ea872
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175813"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="f56d3-102">IMetaDataEmit::DefineNestedType 메서드</span><span class="sxs-lookup"><span data-stu-id="f56d3-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="f56d3-103">형식 정의의 메타데이터 서명을 만들고 `mdTypeDef` 해당 형식에 대한 토큰을 반환하며 정의된 형식이 `tdEncloser` 매개 변수에서 참조하는 형식의 멤버임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f56d3-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f56d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="f56d3-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f56d3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f56d3-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="f56d3-106">【인】 유니코드의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f56d3-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="f56d3-107">【인】 `TypeDef` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f56d3-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="f56d3-108">이것은 값의 `CorTypeAttr` 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="f56d3-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="f56d3-109">【인】 기본 클래스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f56d3-109">[in] The token of the base class.</span></span> <span data-ttu-id="f56d3-110">이것은 또는 `mdTypeDef` 토큰입니다. `mdTypeRef`</span><span class="sxs-lookup"><span data-stu-id="f56d3-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="f56d3-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="f56d3-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="f56d3-112">【인】 이 클래스 또는 인터페이스가 구현하는 인터페이스를 지정하는 토큰 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f56d3-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="f56d3-113">【인】 둘러싸는 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f56d3-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="f56d3-114">배열의 마지막 요소는 . `mdTokenNil`</span><span class="sxs-lookup"><span data-stu-id="f56d3-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="f56d3-115">【아웃】 할당된 토큰입니다. `mdTypeDef`</span><span class="sxs-lookup"><span data-stu-id="f56d3-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f56d3-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f56d3-116">Requirements</span></span>  
 <span data-ttu-id="f56d3-117">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f56d3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f56d3-118">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="f56d3-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f56d3-119">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="f56d3-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f56d3-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f56d3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f56d3-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f56d3-121">See also</span></span>

- [<span data-ttu-id="f56d3-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f56d3-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f56d3-123">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f56d3-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
