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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0b41c03f5e6e08144ae566a3543d352c168555f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472111"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="c3618-102">IMetaDataTables::GetGuidHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="c3618-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="c3618-103">GUID 힙 바이트의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3618-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3618-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3618-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3618-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3618-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="c3618-106">[out] GUID 힙 바이트의 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3618-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3618-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3618-107">Requirements</span></span>  
 <span data-ttu-id="c3618-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3618-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3618-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c3618-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3618-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="c3618-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3618-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3618-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3618-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3618-112">See also</span></span>
- [<span data-ttu-id="c3618-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3618-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c3618-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3618-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
