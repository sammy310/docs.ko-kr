---
title: IMetaDataFilter::MarkToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::MarkToken
helpviewer_keywords:
- IMetaDataFilter::MarkToken method [.NET Framework metadata]
- MarkToken method, IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: bd492834-6529-4d39-b93d-f8cdbd3e297f
topic_type:
- apiref
ms.openlocfilehash: ae105a60969e819f7974735ed8f075c60ba93916
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440354"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="480a2-102">IMetaDataFilter::MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="480a2-102">IMetaDataFilter::MarkToken Method</span></span>
<span data-ttu-id="480a2-103">Sets a value indicating that the specified metadata token has been processed.</span><span class="sxs-lookup"><span data-stu-id="480a2-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="480a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="480a2-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="480a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="480a2-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="480a2-106">[in] The token to mark as processed.</span><span class="sxs-lookup"><span data-stu-id="480a2-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="480a2-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="480a2-107">Requirements</span></span>  
 <span data-ttu-id="480a2-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="480a2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="480a2-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="480a2-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="480a2-110">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="480a2-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="480a2-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="480a2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="480a2-112">참조</span><span class="sxs-lookup"><span data-stu-id="480a2-112">See also</span></span>

- [<span data-ttu-id="480a2-113">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="480a2-113">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
