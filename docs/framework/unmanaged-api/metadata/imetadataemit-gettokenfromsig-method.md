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
ms.openlocfilehash: f1262181fa745e1b6d3fc48a4ad728c1020705b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434322"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="f0767-102">IMetaDataEmit::GetTokenFromSig 메서드</span><span class="sxs-lookup"><span data-stu-id="f0767-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="f0767-103">지정 된 메타 데이터 시그니처의 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f0767-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0767-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0767-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0767-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0767-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="f0767-106">진행 유지 되 고 저장 되는 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="f0767-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="f0767-107">진행 `pvSig`바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f0767-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="f0767-108">제한이 할당 된 `mdSignature` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f0767-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0767-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0767-109">Requirements</span></span>  
 <span data-ttu-id="f0767-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0767-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0767-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f0767-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f0767-112">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0767-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0767-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0767-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0767-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0767-114">See also</span></span>

- [<span data-ttu-id="f0767-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0767-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f0767-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0767-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
