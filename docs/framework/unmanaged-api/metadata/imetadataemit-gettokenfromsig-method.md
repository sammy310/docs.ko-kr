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
ms.openlocfilehash: d02943f28435fc00aad8e319aa260a24cca5e307
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177598"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="0b21d-102">IMetaDataEmit::GetTokenFromSig 메서드</span><span class="sxs-lookup"><span data-stu-id="0b21d-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="0b21d-103">지정된 메타데이터 서명에 대한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b21d-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b21d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0b21d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b21d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b21d-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="0b21d-106">【인】 유지 및 저장할 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="0b21d-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="0b21d-107">【인】 의 바이트 `pvSig`수입니다.</span><span class="sxs-lookup"><span data-stu-id="0b21d-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="0b21d-108">【아웃】 할당된 토큰입니다. `mdSignature`</span><span class="sxs-lookup"><span data-stu-id="0b21d-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b21d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b21d-109">Requirements</span></span>  
 <span data-ttu-id="0b21d-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b21d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b21d-111">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="0b21d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0b21d-112">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0b21d-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b21d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b21d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b21d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b21d-114">See also</span></span>

- [<span data-ttu-id="0b21d-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b21d-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0b21d-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b21d-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
