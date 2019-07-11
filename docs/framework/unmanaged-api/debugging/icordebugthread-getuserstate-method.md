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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7d3325c8aee44849ff1fb7a6cc06a0ed7c2c6f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769095"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="0b189-102">ICorDebugThread::GetUserState 메서드</span><span class="sxs-lookup"><span data-stu-id="0b189-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="0b189-103">이 ICorDebugThread의 현재 사용자 상태를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b189-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b189-104">구문</span><span class="sxs-lookup"><span data-stu-id="0b189-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b189-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b189-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="0b189-106">[out] 이 스레드의 현재 사용자 상태를 설명 하는 CorDebugUserState 열거형 값의 비트 조합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0b189-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b189-107">설명</span><span class="sxs-lookup"><span data-stu-id="0b189-107">Remarks</span></span>  
 <span data-ttu-id="0b189-108">스레드의 사용자 상태는 디버깅 중인 프로그램에서 검사할 때 스레드의 상태를입니다.</span><span class="sxs-lookup"><span data-stu-id="0b189-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="0b189-109">스레드는 여러 상태 비트 집합이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b189-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b189-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b189-110">Requirements</span></span>  
 <span data-ttu-id="0b189-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0b189-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b189-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b189-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b189-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b189-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b189-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b189-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
