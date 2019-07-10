---
title: IMetaDataEmit::SetParent 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6006c8892f650eec9528074d54f030d84ee8f88
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750891"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="06c7b-102">IMetaDataEmit::SetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="06c7b-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="06c7b-103">설정에 대 한 이전 호출에 의해 정의 된 지정된 된 멤버 [imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)에 대 한 이전 호출에서 정의 된 대로 지정 된 형식의 멤버는 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06c7b-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06c7b-104">구문</span><span class="sxs-lookup"><span data-stu-id="06c7b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06c7b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06c7b-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="06c7b-106">[in] `mdMemberRef` 토큰을 새 부모를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c7b-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="06c7b-107">[in] `mdToken` 새 부모입니다.</span><span class="sxs-lookup"><span data-stu-id="06c7b-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06c7b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06c7b-108">Requirements</span></span>  
 <span data-ttu-id="06c7b-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="06c7b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06c7b-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="06c7b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06c7b-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="06c7b-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06c7b-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06c7b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c7b-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="06c7b-113">See also</span></span>

- [<span data-ttu-id="06c7b-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06c7b-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="06c7b-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06c7b-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
