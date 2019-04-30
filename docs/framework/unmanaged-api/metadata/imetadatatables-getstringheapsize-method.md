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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fe6559eca2fef1c9481c8996b19ffb8a08c6019
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049754"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="5c6cb-102">IMetaDataTables::GetStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="5c6cb-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="5c6cb-103">문자열 힙에 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5c6cb-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c6cb-104">Syntax</span></span>  
  
```  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c6cb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c6cb-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="5c6cb-106">[out] 문자열 힙의 바이트의 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5c6cb-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c6cb-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c6cb-107">Requirements</span></span>  
 <span data-ttu-id="5c6cb-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c6cb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c6cb-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5c6cb-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c6cb-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5c6cb-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c6cb-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c6cb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c6cb-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="5c6cb-112">See also</span></span>

- [<span data-ttu-id="5c6cb-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c6cb-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="5c6cb-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c6cb-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
