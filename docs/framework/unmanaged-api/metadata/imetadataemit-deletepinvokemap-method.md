---
title: IMetaDataEmit::DeletePinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
ms.openlocfilehash: 1621e955795fcdbb651114c60eb6a1126a23d037
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434351"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="5eeec-102">IMetaDataEmit::DeletePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="5eeec-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="5eeec-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="5eeec-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eeec-104">구문</span><span class="sxs-lookup"><span data-stu-id="5eeec-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5eeec-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5eeec-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="5eeec-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span><span class="sxs-lookup"><span data-stu-id="5eeec-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eeec-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5eeec-107">Requirements</span></span>  
 <span data-ttu-id="5eeec-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5eeec-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eeec-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5eeec-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5eeec-110">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5eeec-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5eeec-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eeec-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eeec-112">참조</span><span class="sxs-lookup"><span data-stu-id="5eeec-112">See also</span></span>

- [<span data-ttu-id="5eeec-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eeec-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5eeec-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eeec-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
