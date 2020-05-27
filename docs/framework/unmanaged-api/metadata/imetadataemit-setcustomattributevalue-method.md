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
ms.openlocfilehash: 6e24db7da7abbdb597b8ff64515e8053667af3ff
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008770"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="880d6-102">IMetaDataEmit::SetCustomAttributeValue 메서드</span><span class="sxs-lookup"><span data-stu-id="880d6-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="880d6-103">[IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md)에 대 한 이전 호출에서 정의한 사용자 지정 특성의 값을 설정 하거나 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="880d6-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="880d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="880d6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (
    [in]  mdCustomAttribute       pcv,
    [in]  void const              *pCustomAttribute,
    [in]  ULONG                   cbCustomAttribute
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="880d6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="880d6-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="880d6-106">진행 대상 사용자 지정 특성의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="880d6-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="880d6-107">진행 사용자 지정 특성이 포함 된 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="880d6-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="880d6-108">진행 사용자 지정 특성의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="880d6-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="880d6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="880d6-109">Requirements</span></span>  
 <span data-ttu-id="880d6-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="880d6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="880d6-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="880d6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="880d6-112">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="880d6-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="880d6-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="880d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="880d6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="880d6-114">See also</span></span>

- [<span data-ttu-id="880d6-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="880d6-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="880d6-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="880d6-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
