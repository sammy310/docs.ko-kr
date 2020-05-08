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
ms.openlocfilehash: 64d9db09b3e604247ab6a26cdca9eca22adbaace
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976306"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="cb2b7-102">ICorDebugEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="cb2b7-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="cb2b7-103">지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb2b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb2b7-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb2b7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb2b7-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cb2b7-106">진행 커서를 앞으로 이동 하는 기준이 되는 항목의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb2b7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb2b7-107">Requirements</span></span>  
 <span data-ttu-id="cb2b7-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb2b7-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb2b7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb2b7-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb2b7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb2b7-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb2b7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb2b7-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb2b7-112">See also</span></span>

- [<span data-ttu-id="cb2b7-113">ICorDebugEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb2b7-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
