---
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
ms.openlocfilehash: 841af546cc3586529fe290c69e686438f634b90d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377792"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="7e35e-102">ICorDebugThread2::GetTaskID 메서드</span><span class="sxs-lookup"><span data-stu-id="7e35e-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="7e35e-103">이 스레드에서 실행 중인 작업의 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e35e-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e35e-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e35e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e35e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e35e-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="7e35e-106">제한이 이 ICorDebugThread2 개체가 나타내는 스레드에서 실행 중인 작업의 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7e35e-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e35e-107">설명</span><span class="sxs-lookup"><span data-stu-id="7e35e-107">Remarks</span></span>  
 <span data-ttu-id="7e35e-108">스레드가 연결과 연결 된 경우에만 스레드에서 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e35e-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="7e35e-109">`GetTaskID``pTaskId`스레드가 연결과 연결 되어 있지 않으면에서 0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e35e-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e35e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e35e-110">Requirements</span></span>  
 <span data-ttu-id="7e35e-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e35e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e35e-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e35e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e35e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e35e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e35e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e35e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
