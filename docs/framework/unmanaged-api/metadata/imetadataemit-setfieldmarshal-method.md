---
title: IMetaDataEmit::SetFieldMarshal 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
ms.openlocfilehash: cdbcdb9359d295ad9bed2050ed36499feba74d9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442269"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="06ae0-102">IMetaDataEmit::SetFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="06ae0-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="06ae0-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="06ae0-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ae0-104">구문</span><span class="sxs-lookup"><span data-stu-id="06ae0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06ae0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06ae0-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="06ae0-106">[in] The token for target data item.</span><span class="sxs-lookup"><span data-stu-id="06ae0-106">[in] The token for target data item.</span></span> <span data-ttu-id="06ae0-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="06ae0-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="06ae0-108">[in] The signature for unmanaged type.</span><span class="sxs-lookup"><span data-stu-id="06ae0-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="06ae0-109">[in] The count of bytes in `pvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="06ae0-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06ae0-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06ae0-110">Requirements</span></span>  
 <span data-ttu-id="06ae0-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06ae0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06ae0-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="06ae0-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06ae0-113">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06ae0-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06ae0-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06ae0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ae0-115">참조</span><span class="sxs-lookup"><span data-stu-id="06ae0-115">See also</span></span>

- [<span data-ttu-id="06ae0-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06ae0-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="06ae0-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06ae0-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
