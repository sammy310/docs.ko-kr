---
description: '자세히 알아보기: IMetaDataFilter:: IsTokenMarked 메서드'
title: IMetaDataFilter::IsTokenMarked 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
ms.openlocfilehash: dddb0aa9040a2f5ef3ec972bb37a9e8778ddffe8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677788"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="d98b8-103">IMetaDataFilter::IsTokenMarked 메서드</span><span class="sxs-lookup"><span data-stu-id="d98b8-103">IMetaDataFilter::IsTokenMarked Method</span></span>

<span data-ttu-id="d98b8-104">지정 된 메타 데이터 토큰이 처리 된 것으로 표시 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d98b8-104">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d98b8-105">구문</span><span class="sxs-lookup"><span data-stu-id="d98b8-105">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d98b8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d98b8-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="d98b8-107">진행 처리 표시를 검사할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d98b8-107">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="d98b8-108">제한이 이 처리 되었으면이 `true` `tk` 고, 그렇지 않으면 인 값입니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="d98b8-108">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d98b8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d98b8-109">Requirements</span></span>  

 <span data-ttu-id="d98b8-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d98b8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d98b8-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d98b8-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d98b8-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d98b8-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d98b8-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d98b8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d98b8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d98b8-114">See also</span></span>

- [<span data-ttu-id="d98b8-115">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d98b8-115">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
