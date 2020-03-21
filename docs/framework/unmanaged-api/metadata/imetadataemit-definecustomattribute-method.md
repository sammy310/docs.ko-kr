---
title: IMetaDataEmit::DefineCustomAttribute 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
ms.openlocfilehash: 9c4ed282e259aa46fc0cb0175214dc51d3d5fbee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175891"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="f2626-102">IMetaDataEmit::DefineCustomAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="f2626-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="f2626-103">지정된 메타데이터 시그니처를 사용하여 사용자 지정 특성에 대한 정의를 만들고 지정된 개체에 연결되고 해당 사용자 지정 특성 정의에 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f2626-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2626-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2626-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2626-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2626-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="f2626-106">【인】 소유자 항목에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f2626-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="f2626-107">【인】 사용자 지정 특성을 식별하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f2626-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="f2626-108">【인】 사용자 지정 특성에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f2626-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="f2626-109">【인】 의 바이트 `pCustomAttribute`수입니다.</span><span class="sxs-lookup"><span data-stu-id="f2626-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="f2626-110">【아웃】 할당된 토큰입니다. `mdCustomAttribute`</span><span class="sxs-lookup"><span data-stu-id="f2626-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2626-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2626-111">Requirements</span></span>  
 <span data-ttu-id="f2626-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2626-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2626-113">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="f2626-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2626-114">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="f2626-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2626-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2626-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2626-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2626-116">See also</span></span>

- [<span data-ttu-id="f2626-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2626-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f2626-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2626-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
