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
ms.openlocfilehash: 031996813718a074eebab62ff54a2de52b898c22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450219"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="ce7d2-102">IMetaDataEmit::DefineTypeDef 메서드</span><span class="sxs-lookup"><span data-stu-id="ce7d2-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="ce7d2-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce7d2-104">구문</span><span class="sxs-lookup"><span data-stu-id="ce7d2-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce7d2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ce7d2-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="ce7d2-106">[in] The name of the type in Unicode.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="ce7d2-107">[in] `TypeDef` attributes.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="ce7d2-108">This is a bitmask of `CoreTypeAttr` values.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="ce7d2-109">[in] The token of the base class.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-109">[in] The token of the base class.</span></span> <span data-ttu-id="ce7d2-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="ce7d2-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="ce7d2-112">[out] The `mdTypeDef` token assigned.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce7d2-113">주의</span><span class="sxs-lookup"><span data-stu-id="ce7d2-113">Remarks</span></span>  
 <span data-ttu-id="ce7d2-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="ce7d2-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="ce7d2-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="ce7d2-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="ce7d2-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span><span class="sxs-lookup"><span data-stu-id="ce7d2-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="ce7d2-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="ce7d2-120">The last element in the array must be `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce7d2-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce7d2-121">Requirements</span></span>  
 <span data-ttu-id="ce7d2-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce7d2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce7d2-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ce7d2-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce7d2-124">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce7d2-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce7d2-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce7d2-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7d2-126">참조</span><span class="sxs-lookup"><span data-stu-id="ce7d2-126">See also</span></span>

- [<span data-ttu-id="ce7d2-127">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce7d2-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ce7d2-128">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce7d2-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
