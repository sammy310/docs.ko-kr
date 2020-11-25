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
ms.openlocfilehash: ae88336b9640b68b97522d252b3e8334c20ed9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705867"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="5b13e-102">ICorDebugEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="5b13e-102">ICorDebugEnum::Skip Method</span></span>

<span data-ttu-id="5b13e-103">지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b13e-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b13e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5b13e-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b13e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b13e-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="5b13e-106">진행 커서를 앞으로 이동 하는 기준이 되는 항목의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5b13e-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b13e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b13e-107">Requirements</span></span>  

 <span data-ttu-id="5b13e-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b13e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b13e-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b13e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b13e-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b13e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b13e-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b13e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b13e-112">참조</span><span class="sxs-lookup"><span data-stu-id="5b13e-112">See also</span></span>

- [<span data-ttu-id="5b13e-113">ICorDebugEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b13e-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
