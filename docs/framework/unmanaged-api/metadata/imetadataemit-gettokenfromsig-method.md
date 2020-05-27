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
ms.openlocfilehash: 740dad54bc3a79ff546176abdc35487d89ed8f44
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009251"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="d0984-102">IMetaDataEmit::GetTokenFromSig 메서드</span><span class="sxs-lookup"><span data-stu-id="d0984-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="d0984-103">지정 된 메타 데이터 시그니처의 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0984-104">구문</span><span class="sxs-lookup"><span data-stu-id="d0984-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0984-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0984-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="d0984-106">진행 유지 되 고 저장 되는 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="d0984-107">진행 의 바이트 수 `pvSig` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="d0984-108">제한이 `mdSignature`할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0984-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0984-109">Requirements</span></span>  
 <span data-ttu-id="d0984-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0984-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0984-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d0984-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0984-112">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0984-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0984-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0984-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0984-114">See also</span></span>

- [<span data-ttu-id="d0984-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0984-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d0984-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0984-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
