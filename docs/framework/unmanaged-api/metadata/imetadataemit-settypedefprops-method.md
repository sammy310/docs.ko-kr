---
title: IMetaDataEmit::SetTypeDefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: 3ab29fc8c983b354ad5088d26c547868940ec70a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447721"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="32b1a-102">IMetaDataEmit::SetTypeDefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="32b1a-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="32b1a-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="32b1a-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32b1a-104">구문</span><span class="sxs-lookup"><span data-stu-id="32b1a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32b1a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32b1a-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="32b1a-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="32b1a-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="32b1a-107">[in] `TypeDef` attributes.</span><span class="sxs-lookup"><span data-stu-id="32b1a-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="32b1a-108">This is a bitmask of `CorTypeAttr` values.</span><span class="sxs-lookup"><span data-stu-id="32b1a-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="32b1a-109">[in] The `mdToken` of the base class.</span><span class="sxs-lookup"><span data-stu-id="32b1a-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="32b1a-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span><span class="sxs-lookup"><span data-stu-id="32b1a-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="32b1a-111">[in] An array of tokens for the interfaces that this type implements.</span><span class="sxs-lookup"><span data-stu-id="32b1a-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="32b1a-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="32b1a-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="32b1a-113">The last element of the array is must be `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="32b1a-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32b1a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32b1a-114">Requirements</span></span>  
 <span data-ttu-id="32b1a-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32b1a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32b1a-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="32b1a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32b1a-117">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32b1a-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32b1a-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32b1a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b1a-119">참조</span><span class="sxs-lookup"><span data-stu-id="32b1a-119">See also</span></span>

- [<span data-ttu-id="32b1a-120">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32b1a-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="32b1a-121">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32b1a-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
