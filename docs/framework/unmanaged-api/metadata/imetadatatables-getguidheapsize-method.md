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
ms.openlocfilehash: 812794bc76d475c516effdc950ca6a0b877494c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042421"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="69faf-102">IMetaDataTables::GetGuidHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="69faf-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="69faf-103">GUID 힙 바이트의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="69faf-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69faf-104">구문</span><span class="sxs-lookup"><span data-stu-id="69faf-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69faf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="69faf-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="69faf-106">[out] GUID 힙 바이트의 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="69faf-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69faf-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69faf-107">Requirements</span></span>  
 <span data-ttu-id="69faf-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="69faf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69faf-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="69faf-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69faf-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="69faf-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69faf-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69faf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69faf-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="69faf-112">See also</span></span>

- [<span data-ttu-id="69faf-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69faf-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="69faf-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69faf-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
