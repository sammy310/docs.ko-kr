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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 255e2ced8cf7ed06234f8eb8e5423c0bd6541e9a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484526"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="bc5ef-102">IMetaDataFilter::MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="bc5ef-102">IMetaDataFilter::MarkToken Method</span></span>
<span data-ttu-id="bc5ef-103">지정 된 메타 데이터 토큰을 처리 했는지를 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc5ef-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc5ef-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc5ef-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc5ef-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc5ef-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="bc5ef-106">[in] 토큰 처리 됨으로입니다.</span><span class="sxs-lookup"><span data-stu-id="bc5ef-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc5ef-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc5ef-107">Requirements</span></span>  
 <span data-ttu-id="bc5ef-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc5ef-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc5ef-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bc5ef-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc5ef-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="bc5ef-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc5ef-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc5ef-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc5ef-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="bc5ef-112">See also</span></span>
- [<span data-ttu-id="bc5ef-113">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc5ef-113">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
