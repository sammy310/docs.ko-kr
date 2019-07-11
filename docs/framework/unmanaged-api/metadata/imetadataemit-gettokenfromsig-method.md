---
title: IMetaDataEmit::GetTokenFromSig 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: afc2192fe46ed75ed6fb75e0d58268152856b746
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770771"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="9675e-102">IMetaDataEmit::GetTokenFromSig 메서드</span><span class="sxs-lookup"><span data-stu-id="9675e-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="9675e-103">지정 된 메타 데이터 서명에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9675e-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9675e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9675e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9675e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9675e-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="9675e-106">[in] 유지 되 고 저장 된 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="9675e-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="9675e-107">[in] 바이트 수가 `pvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="9675e-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="9675e-108">[out] `mdSignature` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9675e-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9675e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9675e-109">Requirements</span></span>  
 <span data-ttu-id="9675e-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9675e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9675e-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9675e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9675e-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="9675e-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9675e-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9675e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9675e-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="9675e-114">See also</span></span>

- [<span data-ttu-id="9675e-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9675e-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9675e-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9675e-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
