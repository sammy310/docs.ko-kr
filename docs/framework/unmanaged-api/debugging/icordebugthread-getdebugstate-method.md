---
title: ICorDebugThread::GetDebugState 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68df19120f2e0b45e73f9d5e137afc8a5e7ac513
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489893"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="7dfa2-102">ICorDebugThread::GetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="7dfa2-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="7dfa2-103">이 ICorDebugThread 개체의 현재 디버그 상태를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7dfa2-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dfa2-104">구문</span><span class="sxs-lookup"><span data-stu-id="7dfa2-104">Syntax</span></span>  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dfa2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7dfa2-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="7dfa2-106">[out] 이 스레드의 현재 디버그 상태를 설명 하는 CorDebugThreadState 열거형 값의 비트 조합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7dfa2-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dfa2-107">설명</span><span class="sxs-lookup"><span data-stu-id="7dfa2-107">Remarks</span></span>  
 <span data-ttu-id="7dfa2-108">현재 프로세스를 중지할 경우 `pState` 프로세스가 계속 될이 스레드에 대 한 현재의 실제 상태 되지 경우이 스레드에 대 한 존재 하도록 디버그 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7dfa2-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dfa2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7dfa2-109">Requirements</span></span>  
 <span data-ttu-id="7dfa2-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7dfa2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dfa2-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7dfa2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7dfa2-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dfa2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7dfa2-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dfa2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
