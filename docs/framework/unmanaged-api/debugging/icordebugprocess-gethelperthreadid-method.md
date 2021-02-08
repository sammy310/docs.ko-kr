---
description: '자세히 알아보기: ICorDebugProcess:: GetHelperThreadID 메서드'
title: ICorDebugProcess::GetHelperThreadID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
ms.openlocfilehash: ee7bd2106a37c5c67df48a54ff9ab7fa49a03f80
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801022"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="37469-103">ICorDebugProcess::GetHelperThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="37469-103">ICorDebugProcess::GetHelperThreadID Method</span></span>

<span data-ttu-id="37469-104">디버거의 내부 도우미 스레드의 OS (운영 체제) 스레드 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37469-104">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37469-105">구문</span><span class="sxs-lookup"><span data-stu-id="37469-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37469-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37469-106">Parameters</span></span>  

 `pThreadID`  
 <span data-ttu-id="37469-107">제한이 디버거의 내부 도우미 스레드의 OS 스레드 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37469-107">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37469-108">설명</span><span class="sxs-lookup"><span data-stu-id="37469-108">Remarks</span></span>  

 <span data-ttu-id="37469-109">관리 및 관리 되지 않는 디버깅을 수행 하는 동안 디버거에서 지정한 중단점에 도달 하면 지정 된 ID를 가진 스레드가 계속 실행 되도록 하는 것이 디버거의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="37469-109">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="37469-110">디버거는 사용자 로부터이 스레드를 숨기려는 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37469-110">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="37469-111">프로세스에 도우미 스레드를 아직 존재 하지 않는 경우 `GetHelperThreadID` 메서드는 \*에서 0을 반환 합니다 `pThreadID` .</span><span class="sxs-lookup"><span data-stu-id="37469-111">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="37469-112">도우미 스레드의 스레드 ID는 시간이 지남에 따라 변경 될 수 있으므로 캐시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37469-112">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="37469-113">모든 중지 이벤트에서 스레드 ID를 다시 쿼리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37469-113">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="37469-114">디버거의 도우미 스레드의 스레드 ID는 모든 관리 되지 않는 [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) 이벤트에서 올바릅니다. 따라서 디버거가 도우미 스레드의 스레드 id를 확인 하 고 사용자 로부터 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37469-114">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="37469-115">관리 되지 않는 이벤트 중에 도우미 스레드로 식별 되는 스레드는 `ICorDebugManagedCallback::CreateThread` 관리 되는 사용자 코드를 실행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37469-115">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37469-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37469-116">Requirements</span></span>  

 <span data-ttu-id="37469-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37469-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37469-118">**헤더:** CorDebug 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37469-118">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="37469-119">CorDebug .h</span><span class="sxs-lookup"><span data-stu-id="37469-119">CorDebug.h</span></span>  
  
 <span data-ttu-id="37469-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37469-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37469-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37469-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
