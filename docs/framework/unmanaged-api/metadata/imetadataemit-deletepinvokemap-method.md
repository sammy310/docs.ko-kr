---
description: IMetaDataEmit::D eletePinvokeMap 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 977fd600600cdfba0fd9fd5d383648ffbf63229f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783978"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="b12c2-103">IMetaDataEmit::DeletePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="b12c2-103">IMetaDataEmit::DeletePinvokeMap Method</span></span>

<span data-ttu-id="b12c2-104">지정 된 토큰이 참조 하는 개체에 대 한 PInvoke 매핑 메타 데이터를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12c2-104">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b12c2-105">구문</span><span class="sxs-lookup"><span data-stu-id="b12c2-105">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b12c2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b12c2-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="b12c2-107">진행 `mdFieldDef` `mdMethodDef` PInvoke 매핑 메타 데이터를 삭제할 개체를 나타내는 또는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b12c2-107">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b12c2-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b12c2-108">Requirements</span></span>  

 <span data-ttu-id="b12c2-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b12c2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b12c2-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b12c2-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b12c2-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b12c2-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b12c2-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b12c2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12c2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b12c2-113">See also</span></span>

- [<span data-ttu-id="b12c2-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b12c2-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b12c2-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b12c2-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
