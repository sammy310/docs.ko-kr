---
title: ICorDebugController::IsRunning 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.IsRunning
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type:
- apiref
ms.openlocfilehash: f24c07a654dc2345cb65226463573576a6fb3658
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125348"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="6aca5-102">ICorDebugController::IsRunning 메서드</span><span class="sxs-lookup"><span data-stu-id="6aca5-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="6aca5-103">프로세스의 스레드가 현재 자유롭게 실행 중인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6aca5-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aca5-104">구문</span><span class="sxs-lookup"><span data-stu-id="6aca5-104">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aca5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6aca5-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="6aca5-106">제한이 프로세스의 스레드가 자유롭게 실행 되는 경우 `true` 되는 값에 대 한 포인터입니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="6aca5-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aca5-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6aca5-107">Requirements</span></span>  
 <span data-ttu-id="6aca5-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aca5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aca5-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6aca5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6aca5-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6aca5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6aca5-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aca5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aca5-112">참조</span><span class="sxs-lookup"><span data-stu-id="6aca5-112">See also</span></span>
