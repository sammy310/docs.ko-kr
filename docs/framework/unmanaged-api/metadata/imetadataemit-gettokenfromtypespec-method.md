---
title: IMetaDataEmit::GetTokenFromTypeSpec 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 8c609d730297881c0ac20dca8569f0e9492638e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175722"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="2a3da-102">IMetaDataEmit::GetTokenFromTypeSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="2a3da-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="2a3da-103">지정된 메타데이터 시그니처가 있는 형식에 대한 메타데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a3da-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3da-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a3da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a3da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a3da-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="2a3da-106">【인】 정의되는 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="2a3da-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="2a3da-107">【인】 의 바이트 `pvSig`수입니다.</span><span class="sxs-lookup"><span data-stu-id="2a3da-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="2a3da-108">【아웃】 할당된 토큰입니다. `mdTypeSpec`</span><span class="sxs-lookup"><span data-stu-id="2a3da-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a3da-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a3da-109">Requirements</span></span>  
 <span data-ttu-id="2a3da-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a3da-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a3da-111">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="2a3da-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a3da-112">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="2a3da-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a3da-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a3da-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3da-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a3da-114">See also</span></span>

- [<span data-ttu-id="2a3da-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a3da-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2a3da-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a3da-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
