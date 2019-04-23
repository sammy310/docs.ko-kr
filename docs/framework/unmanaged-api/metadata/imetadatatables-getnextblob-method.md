---
title: IMetaDataTables::GetNextBlob 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b8a91a2c1ef9b68dcfc293a870ce3e9b9499a8f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204603"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="6e1fc-102">IMetaDataTables::GetNextBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="6e1fc-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="6e1fc-103">테이블의 다음 binary large object (BLOB)의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e1fc-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e1fc-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e1fc-104">Syntax</span></span>  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e1fc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e1fc-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="6e1fc-106">[in] Blob 열에서 반환 된 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="6e1fc-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="6e1fc-107">[out] 다음 BLOB의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e1fc-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e1fc-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e1fc-108">Requirements</span></span>  
 <span data-ttu-id="6e1fc-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e1fc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e1fc-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e1fc-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e1fc-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="6e1fc-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e1fc-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e1fc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e1fc-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e1fc-113">See also</span></span>

- [<span data-ttu-id="6e1fc-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e1fc-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="6e1fc-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e1fc-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
