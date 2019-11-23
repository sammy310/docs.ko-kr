---
title: IMetaDataEmit::DefineCustomAttribute 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
ms.openlocfilehash: e6a732b98ae02ba2b273b45921b7de61ab4fd29f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432644"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="3f653-102">IMetaDataEmit::DefineCustomAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="3f653-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="3f653-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span><span class="sxs-lookup"><span data-stu-id="3f653-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f653-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f653-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f653-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f653-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="3f653-106">[in] The token for the owner item.</span><span class="sxs-lookup"><span data-stu-id="3f653-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="3f653-107">[in] The token that identifies the custom attribute.</span><span class="sxs-lookup"><span data-stu-id="3f653-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="3f653-108">[in] A pointer to the custom attribute.</span><span class="sxs-lookup"><span data-stu-id="3f653-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="3f653-109">[in] The count of bytes in `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="3f653-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="3f653-110">[out] The `mdCustomAttribute` token assigned.</span><span class="sxs-lookup"><span data-stu-id="3f653-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f653-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f653-111">Requirements</span></span>  
 <span data-ttu-id="3f653-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f653-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f653-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3f653-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f653-114">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f653-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f653-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f653-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f653-116">참조</span><span class="sxs-lookup"><span data-stu-id="3f653-116">See also</span></span>

- [<span data-ttu-id="3f653-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f653-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3f653-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f653-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
