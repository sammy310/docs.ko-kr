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
ms.openlocfilehash: 28a5f79f6fa8d25fd254c4093b0f76e0308edbad
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492527"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="06d66-102">IMetaDataFilter::MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="06d66-102">IMetaDataFilter::MarkToken Method</span></span>
<span data-ttu-id="06d66-103">지정 된 메타 데이터 토큰이 처리 되었음을 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06d66-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d66-104">구문</span><span class="sxs-lookup"><span data-stu-id="06d66-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06d66-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06d66-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="06d66-106">진행 처리 된 것으로 표시할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="06d66-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06d66-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06d66-107">Requirements</span></span>  
 <span data-ttu-id="06d66-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06d66-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06d66-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="06d66-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06d66-110">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06d66-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06d66-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06d66-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d66-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06d66-112">See also</span></span>

- [<span data-ttu-id="06d66-113">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06d66-113">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
