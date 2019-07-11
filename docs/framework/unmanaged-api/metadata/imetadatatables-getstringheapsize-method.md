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
ms.openlocfilehash: b842fb4d0853f473ae8e237a42e800cf0af8dc11
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781378"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="85739-102">IMetaDataTables::GetStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="85739-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="85739-103">문자열 힙에 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85739-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85739-104">구문</span><span class="sxs-lookup"><span data-stu-id="85739-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85739-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="85739-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="85739-106">[out] 문자열 힙의 바이트의 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="85739-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85739-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85739-107">Requirements</span></span>  
 <span data-ttu-id="85739-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="85739-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85739-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="85739-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85739-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="85739-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85739-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85739-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85739-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="85739-112">See also</span></span>

- [<span data-ttu-id="85739-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85739-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="85739-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85739-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
