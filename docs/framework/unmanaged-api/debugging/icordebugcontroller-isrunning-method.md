---
description: '자세히 알아보기: ICorDebugController:: IsRunning 메서드'
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
ms.openlocfilehash: 6a0628cc39765d9cb295877d912d92dbb27937da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764582"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="6cf8e-103">ICorDebugController::IsRunning 메서드</span><span class="sxs-lookup"><span data-stu-id="6cf8e-103">ICorDebugController::IsRunning Method</span></span>

<span data-ttu-id="6cf8e-104">프로세스의 스레드가 현재 자유롭게 실행 중인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cf8e-104">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cf8e-105">구문</span><span class="sxs-lookup"><span data-stu-id="6cf8e-105">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cf8e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6cf8e-106">Parameters</span></span>  

 `pbRunning`  
 <span data-ttu-id="6cf8e-107">제한이 `true` 프로세스의 스레드가 자유롭게 실행 되 면이 고, 그렇지 않으면 인 값에 대 한 포인터입니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="6cf8e-107">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cf8e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6cf8e-108">Requirements</span></span>  

 <span data-ttu-id="6cf8e-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cf8e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cf8e-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6cf8e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6cf8e-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cf8e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cf8e-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cf8e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf8e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cf8e-113">See also</span></span>
