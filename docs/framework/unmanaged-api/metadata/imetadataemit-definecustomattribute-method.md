---
description: IMetaDataEmit::D efineCustomAttribute 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 5d802f590525b8b398ac270b1b7f59d122b45b73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753486"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="c8b1f-103">IMetaDataEmit::DefineCustomAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="c8b1f-103">IMetaDataEmit::DefineCustomAttribute Method</span></span>

<span data-ttu-id="c8b1f-104">지정 된 메타 데이터 시그니처를 사용 하 여 지정 된 개체에 연결 되는 사용자 지정 특성에 대 한 정의를 만들고 해당 사용자 지정 특성 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-104">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8b1f-105">구문</span><span class="sxs-lookup"><span data-stu-id="c8b1f-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8b1f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8b1f-106">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="c8b1f-107">진행 소유자 항목의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-107">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="c8b1f-108">진행 사용자 지정 특성을 식별 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-108">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="c8b1f-109">진행 사용자 지정 특성에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-109">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="c8b1f-110">진행 의 바이트 수 `pCustomAttribute` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-110">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="c8b1f-111">제한이 `mdCustomAttribute` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-111">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8b1f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8b1f-112">Requirements</span></span>  

 <span data-ttu-id="c8b1f-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8b1f-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c8b1f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c8b1f-115">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b1f-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8b1f-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8b1f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b1f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8b1f-117">See also</span></span>

- [<span data-ttu-id="c8b1f-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8b1f-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c8b1f-119">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8b1f-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
