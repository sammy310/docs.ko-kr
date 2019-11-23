---
title: IMetaDataEmit::DefineTypeRefByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
ms.openlocfilehash: 3dfdd473b01bfe83def52f957c52e0f4d11375ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434389"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="ba268-102">IMetaDataEmit::DefineTypeRefByName 메서드</span><span class="sxs-lookup"><span data-stu-id="ba268-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="ba268-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span><span class="sxs-lookup"><span data-stu-id="ba268-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba268-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba268-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba268-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba268-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="ba268-106">[in] The token specifying the resolution scope.</span><span class="sxs-lookup"><span data-stu-id="ba268-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="ba268-107">The following token types are valid:</span><span class="sxs-lookup"><span data-stu-id="ba268-107">The following token types are valid:</span></span>  
  
- <span data-ttu-id="ba268-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span><span class="sxs-lookup"><span data-stu-id="ba268-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
- <span data-ttu-id="ba268-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span><span class="sxs-lookup"><span data-stu-id="ba268-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
- <span data-ttu-id="ba268-110">`mdTypeRef`, if the type is a nested type.</span><span class="sxs-lookup"><span data-stu-id="ba268-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
- <span data-ttu-id="ba268-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span><span class="sxs-lookup"><span data-stu-id="ba268-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
- <span data-ttu-id="ba268-112">Null, if the type is defined globally.</span><span class="sxs-lookup"><span data-stu-id="ba268-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="ba268-113">[in] The name of the target type in Unicode.</span><span class="sxs-lookup"><span data-stu-id="ba268-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="ba268-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span><span class="sxs-lookup"><span data-stu-id="ba268-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba268-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba268-115">Requirements</span></span>  
 <span data-ttu-id="ba268-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba268-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba268-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ba268-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba268-118">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba268-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba268-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba268-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba268-120">참조</span><span class="sxs-lookup"><span data-stu-id="ba268-120">See also</span></span>

- [<span data-ttu-id="ba268-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba268-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ba268-122">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba268-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
