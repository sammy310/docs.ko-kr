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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52190583338f1c1ee9183a98d5f4a6cd7236342d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075686"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="12dfa-102">IMetaDataEmit::DefineCustomAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="12dfa-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="12dfa-103">지정된 된 개체에 연결 될 지정 된 메타 데이터 서명을 사용 하 여 사용자 지정 특성에 대 한 정의 만들고 해당 사용자 지정 특성 정의 하는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12dfa-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12dfa-104">구문</span><span class="sxs-lookup"><span data-stu-id="12dfa-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12dfa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12dfa-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="12dfa-106">[in] 소유자 항목에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="12dfa-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="12dfa-107">[in] 사용자 지정 특성을 식별 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="12dfa-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="12dfa-108">[in] 사용자 지정 특성에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="12dfa-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="12dfa-109">[in] 바이트 수가 `pCustomAttribute`합니다.</span><span class="sxs-lookup"><span data-stu-id="12dfa-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="12dfa-110">[out] `mdCustomAttribute` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="12dfa-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12dfa-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12dfa-111">Requirements</span></span>  
 <span data-ttu-id="12dfa-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="12dfa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12dfa-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="12dfa-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12dfa-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="12dfa-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="12dfa-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="12dfa-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="12dfa-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="12dfa-116">See also</span></span>

- [<span data-ttu-id="12dfa-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12dfa-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="12dfa-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12dfa-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
