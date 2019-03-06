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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7eef04dfb305978c81f465ecb37eda75a52f25e4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502954"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="66566-102">ICorDebugController::IsRunning 메서드</span><span class="sxs-lookup"><span data-stu-id="66566-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="66566-103">프로세스의 스레드는 자유롭게 실행 현재 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66566-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66566-104">구문</span><span class="sxs-lookup"><span data-stu-id="66566-104">Syntax</span></span>  
  
```  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66566-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66566-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="66566-106">[out] 값에 대 한 포인터 `true` 자유롭게 그렇지 않은 경우 프로세스의 스레드가 실행 중인 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="66566-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66566-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66566-107">Requirements</span></span>  
 <span data-ttu-id="66566-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="66566-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66566-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66566-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66566-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66566-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66566-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66566-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66566-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="66566-112">See also</span></span>

