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
ms.openlocfilehash: 242618fb2a5ab748132baf68e24240d1ffaf2301
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139843"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="adeb2-102">IMetaDataEmit::GetTokenFromSig 메서드</span><span class="sxs-lookup"><span data-stu-id="adeb2-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="adeb2-103">지정 된 메타 데이터 서명에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="adeb2-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adeb2-104">구문</span><span class="sxs-lookup"><span data-stu-id="adeb2-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adeb2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="adeb2-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="adeb2-106">[in] 유지 되 고 저장 된 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="adeb2-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="adeb2-107">[in] 바이트 수가 `pvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="adeb2-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="adeb2-108">[out] `mdSignature` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="adeb2-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adeb2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="adeb2-109">Requirements</span></span>  
 <span data-ttu-id="adeb2-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="adeb2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adeb2-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="adeb2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="adeb2-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="adeb2-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="adeb2-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="adeb2-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="adeb2-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="adeb2-114">See also</span></span>

- [<span data-ttu-id="adeb2-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="adeb2-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="adeb2-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="adeb2-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
