---
title: IMetaDataEmit::병합 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: 06894f238f9fda3111d5484bb1b2add183a5abb2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448062"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="12240-102">IMetaDataEmit::병합 메서드</span><span class="sxs-lookup"><span data-stu-id="12240-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="12240-103">Adds the specified imported scope to the list of scopes to be merged.</span><span class="sxs-lookup"><span data-stu-id="12240-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12240-104">구문</span><span class="sxs-lookup"><span data-stu-id="12240-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12240-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12240-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="12240-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span><span class="sxs-lookup"><span data-stu-id="12240-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="12240-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span><span class="sxs-lookup"><span data-stu-id="12240-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="12240-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span><span class="sxs-lookup"><span data-stu-id="12240-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12240-109">주의</span><span class="sxs-lookup"><span data-stu-id="12240-109">Remarks</span></span>  
 <span data-ttu-id="12240-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span><span class="sxs-lookup"><span data-stu-id="12240-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12240-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12240-111">Requirements</span></span>  
 <span data-ttu-id="12240-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12240-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12240-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="12240-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12240-114">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12240-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12240-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12240-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12240-116">참조</span><span class="sxs-lookup"><span data-stu-id="12240-116">See also</span></span>

- [<span data-ttu-id="12240-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12240-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="12240-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12240-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
