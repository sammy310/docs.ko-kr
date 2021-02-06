---
description: '자세히 알아보기: ICorDebugThread:: GetUserState 메서드'
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
ms.openlocfilehash: b63b474525534f9e934954ebe660691db90b8b67
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658869"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="62332-103">ICorDebugThread::GetUserState 메서드</span><span class="sxs-lookup"><span data-stu-id="62332-103">ICorDebugThread::GetUserState Method</span></span>

<span data-ttu-id="62332-104">이 ICorDebugThread의 현재 사용자 상태를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62332-104">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62332-105">구문</span><span class="sxs-lookup"><span data-stu-id="62332-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62332-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="62332-106">Parameters</span></span>  

 `pState`  
 <span data-ttu-id="62332-107">제한이 이 스레드의 현재 사용자 상태를 설명 하는 CorDebugUserState 열거형 값의 비트 조합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="62332-107">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62332-108">설명</span><span class="sxs-lookup"><span data-stu-id="62332-108">Remarks</span></span>  

 <span data-ttu-id="62332-109">스레드의 사용자 상태는 디버깅 중인 프로그램에서 해당 스레드를 검사할 때의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="62332-109">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="62332-110">스레드에는 여러 개의 상태 비트가 설정 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62332-110">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62332-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62332-111">Requirements</span></span>  

 <span data-ttu-id="62332-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62332-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62332-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62332-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62332-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62332-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62332-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62332-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
