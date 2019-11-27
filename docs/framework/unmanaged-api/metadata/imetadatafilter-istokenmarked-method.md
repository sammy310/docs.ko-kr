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
ms.openlocfilehash: 10f31d56a9727e99157f49038c19781f12cd9958
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440424"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="924f5-102">IMetaDataFilter::IsTokenMarked 메서드</span><span class="sxs-lookup"><span data-stu-id="924f5-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="924f5-103">지정 된 메타 데이터 토큰이 처리 된 것으로 표시 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="924f5-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="924f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="924f5-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="924f5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="924f5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="924f5-106">진행 처리 표시를 검사할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="924f5-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="924f5-107">제한이 `tk` 처리 된 경우 `true` 하는 값입니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="924f5-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="924f5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="924f5-108">Requirements</span></span>  
 <span data-ttu-id="924f5-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="924f5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="924f5-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="924f5-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="924f5-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="924f5-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="924f5-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="924f5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="924f5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="924f5-113">See also</span></span>

- [<span data-ttu-id="924f5-114">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="924f5-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
