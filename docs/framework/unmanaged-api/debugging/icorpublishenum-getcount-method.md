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
ms.openlocfilehash: 1465a667763c12593c4bc89148d70f85371fcc67
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775565"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="146cf-102">ICorPublishEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="146cf-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="146cf-103">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="146cf-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="146cf-104">구문</span><span class="sxs-lookup"><span data-stu-id="146cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="146cf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="146cf-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="146cf-106">[out] 열거형에는 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="146cf-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="146cf-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="146cf-107">Requirements</span></span>  
 <span data-ttu-id="146cf-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="146cf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="146cf-109">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="146cf-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="146cf-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="146cf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="146cf-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="146cf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="146cf-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="146cf-112">See also</span></span>

- [<span data-ttu-id="146cf-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="146cf-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
