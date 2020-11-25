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
ms.openlocfilehash: 6fc6cf9b7333dd4caad3c5a4b081fecb060c8f86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722091"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="3de85-102">IMetaDataEmit::DeletePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="3de85-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>

<span data-ttu-id="3de85-103">지정 된 토큰이 참조 하는 개체에 대 한 PInvoke 매핑 메타 데이터를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de85-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3de85-104">구문</span><span class="sxs-lookup"><span data-stu-id="3de85-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3de85-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3de85-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="3de85-106">진행 `mdFieldDef` `mdMethodDef` PInvoke 매핑 메타 데이터를 삭제할 개체를 나타내는 또는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3de85-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3de85-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3de85-107">Requirements</span></span>  

 <span data-ttu-id="3de85-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3de85-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3de85-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3de85-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3de85-110">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de85-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3de85-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3de85-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de85-112">참조</span><span class="sxs-lookup"><span data-stu-id="3de85-112">See also</span></span>

- [<span data-ttu-id="3de85-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3de85-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="3de85-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3de85-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
