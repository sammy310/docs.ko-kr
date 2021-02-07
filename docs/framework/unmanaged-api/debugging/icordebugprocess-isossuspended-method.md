---
description: '자세히 알아보기: ICorDebugProcess:: IsOSSuspended 메서드'
title: ICorDebugProcess::IsOSSuspended 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
ms.openlocfilehash: aa5e438418330d9fee51fcdb56a617421df06904
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746771"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="29176-103">ICorDebugProcess::IsOSSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="29176-103">ICorDebugProcess::IsOSSuspended Method</span></span>

<span data-ttu-id="29176-104">디버거에서이 프로세스를 중지 한 결과로 지정 된 스레드가 일시 중단 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="29176-104">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29176-105">구문</span><span class="sxs-lookup"><span data-stu-id="29176-105">Syntax</span></span>  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29176-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29176-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="29176-107">진행 해당 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="29176-107">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="29176-108">제한이 `true` 지정 된 스레드가 일시 중단 되었으면이 고, 그렇지 않으면 인 부울 값에 대 한 포인터 `pbSuspended` 입니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="29176-108">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29176-109">설명</span><span class="sxs-lookup"><span data-stu-id="29176-109">Remarks</span></span>  

 <span data-ttu-id="29176-110">디버거가이 프로세스를 중지 한 결과로 지정 된 스레드가 일시 중단 되 면 지정 된 스레드의 Win32 일시 중단 횟수가 1 씩 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="29176-110">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="29176-111">디버거 UI (사용자 인터페이스)는 사용자에 게 스레드의 OS (운영 체제) 일시 중단 횟수가 표시 되는 경우이 정보를 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="29176-111">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="29176-112">`IsOSSuspended`메서드는 관리 되지 않는 디버깅 컨텍스트에서만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29176-112">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="29176-113">관리 디버깅 중에는 스레드가 OS 일시 중단 되지 않고 협조적으로 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29176-113">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29176-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29176-114">Requirements</span></span>  

 <span data-ttu-id="29176-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29176-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29176-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29176-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29176-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29176-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29176-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29176-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
