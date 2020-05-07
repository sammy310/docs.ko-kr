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
ms.openlocfilehash: 89ea9f221ad55063e4186cc27cc8038334d800d4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892871"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="4bec2-102">ICorDebugController::IsRunning 메서드</span><span class="sxs-lookup"><span data-stu-id="4bec2-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="4bec2-103">프로세스의 스레드가 현재 자유롭게 실행 중인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bec2-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bec2-104">구문</span><span class="sxs-lookup"><span data-stu-id="4bec2-104">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bec2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4bec2-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="4bec2-106">제한이 프로세스의 스레드가 자유롭게 실행 되는 `true` 경우 값에 대 한 포인터입니다. 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="4bec2-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bec2-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4bec2-107">Requirements</span></span>  
 <span data-ttu-id="4bec2-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bec2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bec2-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bec2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bec2-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bec2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bec2-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bec2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bec2-112">참조</span><span class="sxs-lookup"><span data-stu-id="4bec2-112">See also</span></span>
