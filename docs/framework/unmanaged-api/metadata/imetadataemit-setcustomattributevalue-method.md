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
ms.openlocfilehash: fd5e71071de9e6afebc8f1848e0af8835f22c9bf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448128"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="1aad0-102">IMetaDataEmit::SetCustomAttributeValue 메서드</span><span class="sxs-lookup"><span data-stu-id="1aad0-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="1aad0-103">[IMetaDataEmit::D efinecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)에 대 한 이전 호출에서 정의한 사용자 지정 특성의 값을 설정 하거나 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aad0-104">구문</span><span class="sxs-lookup"><span data-stu-id="1aad0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aad0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1aad0-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="1aad0-106">진행 대상 사용자 지정 특성의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="1aad0-107">진행 사용자 지정 특성이 포함 된 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="1aad0-108">진행 사용자 지정 특성의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aad0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1aad0-109">Requirements</span></span>  
 <span data-ttu-id="1aad0-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1aad0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aad0-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1aad0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1aad0-112">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1aad0-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aad0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aad0-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="1aad0-114">See also</span></span>

- [<span data-ttu-id="1aad0-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1aad0-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1aad0-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1aad0-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
