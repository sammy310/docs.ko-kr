---
title: IMetaDataEmit::SetCustomAttributeValue 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a1f248cf800e9c2bf17d7849e449287cfc493f5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737207"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="464d3-102">IMetaDataEmit::SetCustomAttributeValue 메서드</span><span class="sxs-lookup"><span data-stu-id="464d3-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="464d3-103">설정에 대 한 이전 호출에서 정의한 사용자 지정 특성의 값을 업데이트 하거나 [imetadataemit:: Definecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="464d3-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="464d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="464d3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="464d3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="464d3-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="464d3-106">[in] 대상 사용자 지정 특성의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="464d3-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="464d3-107">[in] 사용자 지정 특성을 포함 하는 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="464d3-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="464d3-108">[in] 사용자 지정 특성의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="464d3-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="464d3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="464d3-109">Requirements</span></span>  
 <span data-ttu-id="464d3-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="464d3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="464d3-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="464d3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="464d3-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="464d3-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="464d3-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="464d3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="464d3-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="464d3-114">See also</span></span>

- [<span data-ttu-id="464d3-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="464d3-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="464d3-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="464d3-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
