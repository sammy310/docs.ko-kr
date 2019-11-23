---
title: IMetaDataEmit::SetParent 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: a73afaebc2943190eeeee50367ecd31f1fb59df1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432446"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="4f166-102">IMetaDataEmit::SetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="4f166-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="4f166-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="4f166-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f166-104">구문</span><span class="sxs-lookup"><span data-stu-id="4f166-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f166-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4f166-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="4f166-106">[in] The `mdMemberRef` token to receive a new parent.</span><span class="sxs-lookup"><span data-stu-id="4f166-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="4f166-107">[in] The `mdToken` for the new parent.</span><span class="sxs-lookup"><span data-stu-id="4f166-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f166-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f166-108">Requirements</span></span>  
 <span data-ttu-id="4f166-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f166-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f166-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4f166-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f166-111">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f166-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f166-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f166-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f166-113">참조</span><span class="sxs-lookup"><span data-stu-id="4f166-113">See also</span></span>

- [<span data-ttu-id="4f166-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f166-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4f166-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f166-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
