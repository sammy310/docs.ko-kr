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
ms.openlocfilehash: 096a460f9d6581ebdd00f8487af68f652524d52f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681667"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="30823-102">IMetaDataEmit::DefineCustomAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="30823-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>

<span data-ttu-id="30823-103">지정 된 메타 데이터 시그니처를 사용 하 여 지정 된 개체에 연결 되는 사용자 지정 특성에 대 한 정의를 만들고 해당 사용자 지정 특성 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="30823-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30823-104">구문</span><span class="sxs-lookup"><span data-stu-id="30823-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30823-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="30823-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="30823-106">진행 소유자 항목의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="30823-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="30823-107">진행 사용자 지정 특성을 식별 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="30823-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="30823-108">진행 사용자 지정 특성에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="30823-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="30823-109">진행 의 바이트 수 `pCustomAttribute` 입니다.</span><span class="sxs-lookup"><span data-stu-id="30823-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="30823-110">제한이 `mdCustomAttribute` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="30823-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30823-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30823-111">Requirements</span></span>  

 <span data-ttu-id="30823-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30823-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30823-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="30823-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30823-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30823-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30823-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30823-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30823-116">참조</span><span class="sxs-lookup"><span data-stu-id="30823-116">See also</span></span>

- [<span data-ttu-id="30823-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30823-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="30823-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30823-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
