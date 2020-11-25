---
title: ICorDebugProcess::ThreadForFiberCookie 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ThreadForFiberCookie
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ThreadForFiberCookie
helpviewer_keywords:
- ICorDebugProcess::ThreadForFiberCookie method [.NET Framework debugging]
- ThreadForFiberCookie method [.NET Framework debugging]
ms.assetid: afe4e97f-bffc-47e1-adad-d6e842487f35
topic_type:
- apiref
ms.openlocfilehash: 74cad19d9fa681a6afb933f79ee7061590084509
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694661"
---
# <a name="icordebugprocessthreadforfibercookie-method"></a><span data-ttu-id="d3c3f-102">ICorDebugProcess::ThreadForFiberCookie 메서드</span><span class="sxs-lookup"><span data-stu-id="d3c3f-102">ICorDebugProcess::ThreadForFiberCookie Method</span></span>

<span data-ttu-id="d3c3f-103">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="d3c3f-103">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3c3f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3c3f-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadForFiberCookie (  
    [in] DWORD fiberCookie,  
    [out] ICorDebugThread **ppThread  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d3c3f-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3c3f-105">Requirements</span></span>  

 <span data-ttu-id="d3c3f-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3c3f-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3c3f-107">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3c3f-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3c3f-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3c3f-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3c3f-109">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3c3f-109">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
