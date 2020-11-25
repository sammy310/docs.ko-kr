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
ms.openlocfilehash: 1b524067ac72dfd3bd19475f11d4ec12a307731d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702423"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="eaa7e-102">IMetaDataTables::GetGuidHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="eaa7e-102">IMetaDataTables::GetGuidHeapSize Method</span></span>

<span data-ttu-id="eaa7e-103">GUID 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7e-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaa7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="eaa7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaa7e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eaa7e-105">Parameters</span></span>  

 `pcbGuids`  
 <span data-ttu-id="eaa7e-106">제한이 GUID 힙의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7e-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaa7e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eaa7e-107">Requirements</span></span>  

 <span data-ttu-id="eaa7e-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eaa7e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaa7e-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="eaa7e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eaa7e-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa7e-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eaa7e-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaa7e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaa7e-112">참조</span><span class="sxs-lookup"><span data-stu-id="eaa7e-112">See also</span></span>

- [<span data-ttu-id="eaa7e-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eaa7e-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="eaa7e-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eaa7e-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
