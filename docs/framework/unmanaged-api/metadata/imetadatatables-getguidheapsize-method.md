---
title: IMetaDataTables::GetGuidHeapSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
ms.openlocfilehash: cf455b3fb34d8eed78ffaadffad621062c2b9b22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443500"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="ae151-102">IMetaDataTables::GetGuidHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="ae151-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="ae151-103">Gets the size, in bytes, of the GUID heap.</span><span class="sxs-lookup"><span data-stu-id="ae151-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae151-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae151-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae151-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae151-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="ae151-106">[out] A pointer to the size, in bytes, of the GUID heap.</span><span class="sxs-lookup"><span data-stu-id="ae151-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae151-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae151-107">Requirements</span></span>  
 <span data-ttu-id="ae151-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae151-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae151-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ae151-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae151-110">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ae151-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae151-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae151-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae151-112">참조</span><span class="sxs-lookup"><span data-stu-id="ae151-112">See also</span></span>

- [<span data-ttu-id="ae151-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae151-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="ae151-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae151-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
