---
description: '자세히 알아보기: IMetaDataTables:: GetBlobHeapSize 메서드'
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
ms.openlocfilehash: f6d5c7aeb5e1cc1f307d53d8f3e3cc99daa72311
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688314"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="6cb0e-103">IMetaDataTables::GetBlobHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="6cb0e-103">IMetaDataTables::GetBlobHeapSize Method</span></span>

<span data-ttu-id="6cb0e-104">BLOB (binary large object) 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-104">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cb0e-105">구문</span><span class="sxs-lookup"><span data-stu-id="6cb0e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="6cb0e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6cb0e-106">Parameters</span></span>  

 `pcbBlobs`  
 <span data-ttu-id="6cb0e-107">제한이 BLOB 힙의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-107">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cb0e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6cb0e-108">Requirements</span></span>  

 <span data-ttu-id="6cb0e-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cb0e-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6cb0e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6cb0e-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6cb0e-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cb0e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb0e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cb0e-113">See also</span></span>

- [<span data-ttu-id="6cb0e-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6cb0e-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="6cb0e-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6cb0e-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
