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
ms.openlocfilehash: c942838fb62bf86c4054761f4e7f2ef0518b3d89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701811"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="15094-102">IMetaDataFilter::MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="15094-102">IMetaDataFilter::MarkToken Method</span></span>

<span data-ttu-id="15094-103">지정 된 메타 데이터 토큰이 처리 되었음을 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15094-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15094-104">구문</span><span class="sxs-lookup"><span data-stu-id="15094-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15094-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15094-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="15094-106">진행 처리 된 것으로 표시할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="15094-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15094-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15094-107">Requirements</span></span>  

 <span data-ttu-id="15094-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15094-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15094-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="15094-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15094-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15094-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15094-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15094-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15094-112">참조</span><span class="sxs-lookup"><span data-stu-id="15094-112">See also</span></span>

- [<span data-ttu-id="15094-113">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15094-113">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
