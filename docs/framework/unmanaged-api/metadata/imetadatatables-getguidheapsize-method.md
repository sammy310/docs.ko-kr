---
description: '자세히 알아보기: IMetaDataTables:: GetGuidHeapSize 메서드'
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
ms.openlocfilehash: bbf2fd7e083c5a0a42ad69ab685b3e1aa8321d68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688145"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="5b6c0-103">IMetaDataTables::GetGuidHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="5b6c0-103">IMetaDataTables::GetGuidHeapSize Method</span></span>

<span data-ttu-id="5b6c0-104">GUID 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5b6c0-104">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b6c0-105">구문</span><span class="sxs-lookup"><span data-stu-id="5b6c0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b6c0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b6c0-106">Parameters</span></span>  

 `pcbGuids`  
 <span data-ttu-id="5b6c0-107">제한이 GUID 힙의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6c0-107">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b6c0-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b6c0-108">Requirements</span></span>  

 <span data-ttu-id="5b6c0-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b6c0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b6c0-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="5b6c0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b6c0-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b6c0-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b6c0-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b6c0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6c0-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b6c0-113">See also</span></span>

- [<span data-ttu-id="5b6c0-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b6c0-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="5b6c0-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b6c0-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
