---
title: ICorDebugEnum::Skip 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53b892cddbf716afbd137ead36a69aa42f22d331
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752221"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="446ec-102">ICorDebugEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="446ec-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="446ec-103">열거형에서 항목의 지정된 된 수 만큼 앞으로 커서를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="446ec-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="446ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="446ec-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="446ec-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="446ec-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="446ec-106">[in] 커서를 앞으로 이동에 사용 되는 항목의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="446ec-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="446ec-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="446ec-107">Requirements</span></span>  
 <span data-ttu-id="446ec-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="446ec-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="446ec-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="446ec-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="446ec-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="446ec-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="446ec-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="446ec-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="446ec-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="446ec-112">See also</span></span>

- [<span data-ttu-id="446ec-113">ICorDebugEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="446ec-113">ICorDebugEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
