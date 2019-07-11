---
title: IMetaDataEmit::DeleteFieldMarshal 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 36f9ac10348cb8235c95070ddbc9cb5f47a84bd6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777444"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="a1510-102">IMetaDataEmit::DeleteFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="a1510-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="a1510-103">지정한 토큰이 참조 하는 개체에 대 한 메타 데이터 서명을 마샬링 PInvoke를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1510-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1510-104">구문</span><span class="sxs-lookup"><span data-stu-id="a1510-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1510-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a1510-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="a1510-106">[in] `mdFieldDef` 또는 `mdParamDef` 필드 또는 매개 변수를 마샬링 메타 데이터 서명을 삭제할 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a1510-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1510-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1510-107">Requirements</span></span>  
 <span data-ttu-id="a1510-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a1510-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1510-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a1510-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1510-110">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a1510-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1510-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1510-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1510-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="a1510-112">See also</span></span>

- [<span data-ttu-id="a1510-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1510-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a1510-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1510-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
