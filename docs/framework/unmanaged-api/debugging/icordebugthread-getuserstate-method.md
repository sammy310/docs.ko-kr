---
title: ICorDebugThread::GetUserState 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
ms.openlocfilehash: f3511ff5ee9b9221037c64a5e17d61f6bf52e5f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133426"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="f4fbc-102">ICorDebugThread::GetUserState 메서드</span><span class="sxs-lookup"><span data-stu-id="f4fbc-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="f4fbc-103">이 ICorDebugThread의 현재 사용자 상태를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4fbc-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4fbc-104">구문</span><span class="sxs-lookup"><span data-stu-id="f4fbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4fbc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f4fbc-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="f4fbc-106">제한이 이 스레드의 현재 사용자 상태를 설명 하는 CorDebugUserState 열거형 값의 비트 조합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f4fbc-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4fbc-107">주의</span><span class="sxs-lookup"><span data-stu-id="f4fbc-107">Remarks</span></span>  
 <span data-ttu-id="f4fbc-108">스레드의 사용자 상태는 디버깅 중인 프로그램에서 해당 스레드를 검사할 때의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f4fbc-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="f4fbc-109">스레드에는 여러 개의 상태 비트가 설정 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4fbc-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4fbc-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4fbc-110">Requirements</span></span>  
 <span data-ttu-id="f4fbc-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4fbc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4fbc-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4fbc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4fbc-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4fbc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4fbc-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4fbc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
