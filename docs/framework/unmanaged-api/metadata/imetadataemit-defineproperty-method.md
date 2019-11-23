---
title: IMetaDataEmit::DefineProperty 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: f11b374ed0ecbfc137c43fb641ae691237604691
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431528"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="badf5-102">IMetaDataEmit::DefineProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="badf5-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="badf5-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span><span class="sxs-lookup"><span data-stu-id="badf5-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="badf5-104">구문</span><span class="sxs-lookup"><span data-stu-id="badf5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineProperty (   
    [in]  mdTypeDef          td,   
    [in]  LPCWSTR            szProperty,   
    [in]  DWORD              dwPropFlags,   
    [in]  PCCOR_SIGNATURE    pvSig,   
    [in]  ULONG              cbSig,   
    [in]  DWORD              dwCPlusTypeFlag,   
    [in]  void const         *pValue,   
    [in]  ULONG              cchValue,   
    [in]  mdMethodDef        mdSetter,   
    [in]  mdMethodDef        mdGetter,   
    [in]  mdMethodDef        rmdOtherMethods[],   
    [out] mdProperty         *pmdProp   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="badf5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="badf5-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="badf5-106">[in] The token for class or interface on which the property is being defined.</span><span class="sxs-lookup"><span data-stu-id="badf5-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="badf5-107">[in] The name of the property.</span><span class="sxs-lookup"><span data-stu-id="badf5-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="badf5-108">[in] The property flags.</span><span class="sxs-lookup"><span data-stu-id="badf5-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="badf5-109">[in] The property signature.</span><span class="sxs-lookup"><span data-stu-id="badf5-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="badf5-110">[in] The count of bytes in `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="badf5-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="badf5-111">[in] The type of the property's default value.</span><span class="sxs-lookup"><span data-stu-id="badf5-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="badf5-112">[in] The default value for the property.</span><span class="sxs-lookup"><span data-stu-id="badf5-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="badf5-113">[in] The count of (Unicode) characters in `pValue`.</span><span class="sxs-lookup"><span data-stu-id="badf5-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="badf5-114">[in] The method that sets the property value.</span><span class="sxs-lookup"><span data-stu-id="badf5-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="badf5-115">[in] The method that gets the property value.</span><span class="sxs-lookup"><span data-stu-id="badf5-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="badf5-116">[in] An array of other methods associated with the property.</span><span class="sxs-lookup"><span data-stu-id="badf5-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="badf5-117">Terminate the array with an `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="badf5-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="badf5-118">[out] The `mdProperty` token assigned.</span><span class="sxs-lookup"><span data-stu-id="badf5-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="badf5-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="badf5-119">Requirements</span></span>  
 <span data-ttu-id="badf5-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="badf5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="badf5-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="badf5-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="badf5-122">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="badf5-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="badf5-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="badf5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="badf5-124">참조</span><span class="sxs-lookup"><span data-stu-id="badf5-124">See also</span></span>

- [<span data-ttu-id="badf5-125">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="badf5-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="badf5-126">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="badf5-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
