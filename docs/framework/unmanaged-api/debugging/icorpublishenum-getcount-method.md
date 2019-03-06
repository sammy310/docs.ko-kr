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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c353edf9db0a7bc7ec0a25f712527dc3c9d8cc28
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484656"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="d81e3-102">ICorPublishEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="d81e3-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="d81e3-103">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d81e3-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d81e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="d81e3-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d81e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d81e3-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="d81e3-106">[out] 열거형에는 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d81e3-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d81e3-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d81e3-107">Requirements</span></span>  
 <span data-ttu-id="d81e3-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d81e3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d81e3-109">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="d81e3-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d81e3-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d81e3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d81e3-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d81e3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d81e3-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="d81e3-112">See also</span></span>
- [<span data-ttu-id="d81e3-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d81e3-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
