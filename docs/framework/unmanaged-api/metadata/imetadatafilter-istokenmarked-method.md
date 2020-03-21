---
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
ms.openlocfilehash: 47377e892aaf2bdd96a297630c47fe52215b0564
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177388"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="adc01-102">IMetaDataFilter::IsTokenMarked 메서드</span><span class="sxs-lookup"><span data-stu-id="adc01-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="adc01-103">지정된 메타데이터 토큰이 처리된 것으로 표시되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="adc01-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adc01-104">구문</span><span class="sxs-lookup"><span data-stu-id="adc01-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adc01-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="adc01-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="adc01-106">【인】 처리 표시를 검사할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="adc01-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="adc01-107">【아웃】 처리된 경우값입니다. `true` `tk` 그렇지 `false`않으면 .</span><span class="sxs-lookup"><span data-stu-id="adc01-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adc01-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="adc01-108">Requirements</span></span>  
 <span data-ttu-id="adc01-109">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="adc01-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adc01-110">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="adc01-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="adc01-111">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="adc01-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="adc01-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adc01-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc01-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="adc01-113">See also</span></span>

- [<span data-ttu-id="adc01-114">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="adc01-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
