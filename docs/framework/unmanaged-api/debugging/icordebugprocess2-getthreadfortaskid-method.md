---
title: ICorDebugProcess2::GetThreadForTaskID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetThreadForTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type:
- apiref
ms.openlocfilehash: 89be29c770098d92ce3c47f7c45b1bb8580f2edb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213519"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="475a2-102">ICorDebugProcess2::GetThreadForTaskID 메서드</span><span class="sxs-lookup"><span data-stu-id="475a2-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="475a2-103">지정 된 식별자를 가진 태스크가 실행 중인 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="475a2-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="475a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="475a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="475a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="475a2-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="475a2-106">진행 태스크의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="475a2-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="475a2-107">제한이 검색할 스레드를 나타내는 ICorDebugThread2 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="475a2-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="475a2-108">설명</span><span class="sxs-lookup"><span data-stu-id="475a2-108">Remarks</span></span>  
 <span data-ttu-id="475a2-109">호스트는 [ICLRTask:: SetTaskIdentifier](../hosting/iclrtask-settaskidentifier-method.md) 메서드를 사용 하 여 작업 식별자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475a2-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="475a2-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="475a2-110">Requirements</span></span>  
 <span data-ttu-id="475a2-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="475a2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="475a2-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="475a2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="475a2-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="475a2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="475a2-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="475a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
