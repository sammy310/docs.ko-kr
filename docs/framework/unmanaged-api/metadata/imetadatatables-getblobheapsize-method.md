---
title: IMetaDataTables::GetBlobHeapSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d22e61d28e0fbf06fa1cfe9e9ac18a534726f01d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076457"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="0ba55-102">IMetaDataTables::GetBlobHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="0ba55-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="0ba55-103">(BLOB) 이진 대형 개체 힙 바이트의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ba55-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ba55-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ba55-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="0ba55-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ba55-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="0ba55-106">[out] 크기 (바이트)는 BLOB 힙에서의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0ba55-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ba55-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ba55-107">Requirements</span></span>  
 <span data-ttu-id="0ba55-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ba55-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ba55-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ba55-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ba55-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0ba55-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0ba55-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="0ba55-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ba55-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="0ba55-112">See also</span></span>

- [<span data-ttu-id="0ba55-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ba55-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="0ba55-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ba55-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
