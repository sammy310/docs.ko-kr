---
description: '자세히 알아보기: ICorDebugThread2:: GetTaskID 메서드'
title: ICorDebugThread2::GetTaskID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
ms.openlocfilehash: 5429daee9150d63834c747dd5ebb763dd6f0da6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658687"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="f7d04-103">ICorDebugThread2::GetTaskID 메서드</span><span class="sxs-lookup"><span data-stu-id="f7d04-103">ICorDebugThread2::GetTaskID Method</span></span>

<span data-ttu-id="f7d04-104">이 스레드에서 실행 중인 작업의 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f7d04-104">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7d04-105">구문</span><span class="sxs-lookup"><span data-stu-id="f7d04-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7d04-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7d04-106">Parameters</span></span>  

 `pTaskId`  
 <span data-ttu-id="f7d04-107">제한이 이 ICorDebugThread2 개체가 나타내는 스레드에서 실행 중인 작업의 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f7d04-107">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7d04-108">설명</span><span class="sxs-lookup"><span data-stu-id="f7d04-108">Remarks</span></span>  

 <span data-ttu-id="f7d04-109">스레드가 연결과 연결 된 경우에만 스레드에서 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d04-109">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="f7d04-110">`GetTaskID``pTaskId`스레드가 연결과 연결 되어 있지 않으면에서 0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d04-110">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7d04-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7d04-111">Requirements</span></span>  

 <span data-ttu-id="f7d04-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7d04-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7d04-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7d04-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7d04-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7d04-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7d04-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7d04-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
