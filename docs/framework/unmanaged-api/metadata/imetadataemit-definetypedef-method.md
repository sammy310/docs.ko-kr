---
title: IMetaDataEmit::DefineTypeDef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175761"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="068c6-102">IMetaDataEmit::DefineTypeDef 메서드</span><span class="sxs-lookup"><span data-stu-id="068c6-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="068c6-103">공통 언어 런타임 형식에 대한 형식 정의를 만들고 해당 형식 정의에 대한 메타데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="068c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="068c6-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="068c6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="068c6-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="068c6-106">【인】 유니코드의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="068c6-107">【인】 `TypeDef` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="068c6-108">이것은 값의 `CoreTypeAttr` 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="068c6-109">【인】 기본 클래스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-109">[in] The token of the base class.</span></span> <span data-ttu-id="068c6-110">`mdTypeDef` 토큰 또는 토큰이어야 `mdTypeRef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="068c6-111">【인】 이 클래스 또는 인터페이스가 구현하는 인터페이스를 지정하는 토큰 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="068c6-112">【아웃】 할당된 토큰입니다. `mdTypeDef`</span><span class="sxs-lookup"><span data-stu-id="068c6-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="068c6-113">설명</span><span class="sxs-lookup"><span data-stu-id="068c6-113">Remarks</span></span>  
 <span data-ttu-id="068c6-114">플래그는 `dwTypeDefFlags` 생성되는 형식이 공통 형식 시스템 참조 유형(클래스 또는 인터페이스)인지 또는 공통 형식 시스템 값 형식인지 를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="068c6-115">제공된 매개 변수에 따라 이 메서드는 부작용으로 이 `mdInterfaceImpl` 형식에 의해 상속되거나 구현되는 각 인터페이스에 대한 레코드를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="068c6-116">그러나 이 메서드는 이러한 `mdInterfaceImpl` 토큰을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="068c6-117">클라이언트가 나중에 `mdInterfaceImpl` 토큰을 추가하거나 수정하려면 인터페이스를 `IMetaDataImport` 사용하여 토큰을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="068c6-118">`[default]` 인터페이스의 COM 의미 체계를 사용하려면 기본 인터페이스를 첫 번째 요소로 제공해야 `rtkImplements`합니다. 클래스에 설정된 사용자 지정 특성은 클래스에 기본 인터페이스가 있음을 나타냅니다(항상 `mdInterfaceImpl` 클래스에 대해 선언된 첫 번째 토큰으로 가정됨).</span><span class="sxs-lookup"><span data-stu-id="068c6-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="068c6-119">`rtkImplements` 배열의 각 요소는 `mdTypeDef` 또는 `mdTypeRef` 토큰을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="068c6-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="068c6-120">배열의 마지막 요소는 . `mdTokenNil`</span><span class="sxs-lookup"><span data-stu-id="068c6-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="068c6-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="068c6-121">Requirements</span></span>  
 <span data-ttu-id="068c6-122">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="068c6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="068c6-123">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="068c6-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="068c6-124">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="068c6-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="068c6-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="068c6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="068c6-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="068c6-126">See also</span></span>

- [<span data-ttu-id="068c6-127">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="068c6-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="068c6-128">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="068c6-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
