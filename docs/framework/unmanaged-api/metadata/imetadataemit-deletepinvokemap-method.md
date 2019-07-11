---
title: IMetaDataEmit::DeletePinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64ba852c4bb0ae7b0119876fca4a4b2a107ed934
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777425"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="95e4d-102">IMetaDataEmit::DeletePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="95e4d-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="95e4d-103">지정한 토큰이 참조 하는 개체에 대 한 PInvoke 매핑 메타 데이터를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="95e4d-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e4d-104">구문</span><span class="sxs-lookup"><span data-stu-id="95e4d-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95e4d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95e4d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="95e4d-106">[in] `mdFieldDef` 또는 `mdMethodDef` PInvoke 매핑 메타 데이터를 삭제 하는 개체를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="95e4d-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95e4d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95e4d-107">Requirements</span></span>  
 <span data-ttu-id="95e4d-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95e4d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e4d-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="95e4d-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95e4d-110">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="95e4d-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95e4d-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95e4d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e4d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="95e4d-112">See also</span></span>

- [<span data-ttu-id="95e4d-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95e4d-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="95e4d-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95e4d-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
