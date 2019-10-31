---
title: ICorPublishEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
ms.openlocfilehash: a03b06143c0bd92425c7bfc13af6e374dc629f10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140483"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="5623f-102">ICorPublishEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="5623f-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="5623f-103">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5623f-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5623f-104">구문</span><span class="sxs-lookup"><span data-stu-id="5623f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5623f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5623f-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="5623f-106">제한이 열거형의 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5623f-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5623f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5623f-107">Requirements</span></span>  
 <span data-ttu-id="5623f-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5623f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5623f-109">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="5623f-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5623f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5623f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5623f-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5623f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5623f-112">참조</span><span class="sxs-lookup"><span data-stu-id="5623f-112">See also</span></span>

- [<span data-ttu-id="5623f-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5623f-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
