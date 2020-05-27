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
ms.openlocfilehash: 17757df566ba8d141e7adec00dcc1f75959d0e00
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005630"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="6e258-102">IMetaDataEmit::DefineCustomAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="6e258-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="6e258-103">지정 된 메타 데이터 시그니처를 사용 하 여 지정 된 개체에 연결 되는 사용자 지정 특성에 대 한 정의를 만들고 해당 사용자 지정 특성 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e258-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e258-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e258-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e258-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e258-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="6e258-106">진행 소유자 항목의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6e258-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="6e258-107">진행 사용자 지정 특성을 식별 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6e258-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="6e258-108">진행 사용자 지정 특성에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e258-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="6e258-109">진행 의 바이트 수 `pCustomAttribute` 입니다.</span><span class="sxs-lookup"><span data-stu-id="6e258-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="6e258-110">제한이 `mdCustomAttribute`할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6e258-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e258-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e258-111">Requirements</span></span>  
 <span data-ttu-id="6e258-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e258-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e258-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6e258-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e258-114">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e258-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e258-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e258-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e258-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e258-116">See also</span></span>

- [<span data-ttu-id="6e258-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e258-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="6e258-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e258-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
