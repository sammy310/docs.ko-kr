---
title: IMetaDataTables::GetStringHeapSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
ms.openlocfilehash: 43599a7e39ca4cc9d27dab43a948dc2f04e5010a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426679"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="281d7-102">IMetaDataTables::GetStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="281d7-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="281d7-103">Gets the size, in bytes, of the string heap.</span><span class="sxs-lookup"><span data-stu-id="281d7-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="281d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="281d7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="281d7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="281d7-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="281d7-106">[out] A pointer to the size, in bytes, of the string heap.</span><span class="sxs-lookup"><span data-stu-id="281d7-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="281d7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="281d7-107">Requirements</span></span>  
 <span data-ttu-id="281d7-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="281d7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="281d7-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="281d7-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="281d7-110">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="281d7-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="281d7-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="281d7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="281d7-112">참조</span><span class="sxs-lookup"><span data-stu-id="281d7-112">See also</span></span>

- [<span data-ttu-id="281d7-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="281d7-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="281d7-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="281d7-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
