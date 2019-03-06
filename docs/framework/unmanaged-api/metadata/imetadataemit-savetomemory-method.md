---
title: IMetaDataEmit::SaveToMemory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6e9bb51965b258093321a5dbb19447ec6d6474d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471821"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="38e24-102">IMetaDataEmit::SaveToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="38e24-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="38e24-103">메모리의 지정된 된 영역을 현재 범위에서 모든 메타 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="38e24-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e24-104">구문</span><span class="sxs-lookup"><span data-stu-id="38e24-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38e24-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38e24-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="38e24-106">[out] 메타 데이터 작성을 시작 하는 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="38e24-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="38e24-107">[in] 할당된 된 메모리의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="38e24-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38e24-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38e24-108">Requirements</span></span>  
 <span data-ttu-id="38e24-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="38e24-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38e24-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="38e24-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38e24-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="38e24-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38e24-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38e24-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e24-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="38e24-113">See also</span></span>
- [<span data-ttu-id="38e24-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38e24-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="38e24-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38e24-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
