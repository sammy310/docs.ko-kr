---
description: '자세히 알아보기: IMetaDataFilter:: MarkToken 메서드'
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
ms.openlocfilehash: 97191533ae7d2bdc951521f1929a4c001c521b9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677797"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="efaf1-103">IMetaDataFilter::MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="efaf1-103">IMetaDataFilter::MarkToken Method</span></span>

<span data-ttu-id="efaf1-104">지정 된 메타 데이터 토큰이 처리 되었음을 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efaf1-104">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efaf1-105">구문</span><span class="sxs-lookup"><span data-stu-id="efaf1-105">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efaf1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="efaf1-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="efaf1-107">진행 처리 된 것으로 표시할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="efaf1-107">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efaf1-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="efaf1-108">Requirements</span></span>  

 <span data-ttu-id="efaf1-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efaf1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efaf1-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="efaf1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="efaf1-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efaf1-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="efaf1-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efaf1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efaf1-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="efaf1-113">See also</span></span>

- [<span data-ttu-id="efaf1-114">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efaf1-114">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
