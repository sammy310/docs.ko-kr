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
ms.openlocfilehash: 746fef3629e6573d7dfe47d5a3fcf9ee9a1d4250
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728045"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="1d881-102">ICorDebugThread::GetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="1d881-102">ICorDebugThread::GetDebugState Method</span></span>

<span data-ttu-id="1d881-103">이 ICorDebugThread 개체의 현재 디버그 상태를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1d881-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d881-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d881-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d881-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d881-105">Parameters</span></span>  

 `pState`  
 <span data-ttu-id="1d881-106">제한이 이 스레드의 현재 디버그 상태를 설명 하는 CorDebugThreadState 열거형 값의 비트 조합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1d881-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d881-107">설명</span><span class="sxs-lookup"><span data-stu-id="1d881-107">Remarks</span></span>  

 <span data-ttu-id="1d881-108">프로세스가 현재 중지 된 경우이 스레드의 `pState` 실제 현재 상태가 아닌 프로세스가 계속 되는 경우이 스레드에 대해 존재 하는 디버그 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d881-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d881-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d881-109">Requirements</span></span>  

 <span data-ttu-id="1d881-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d881-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d881-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d881-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d881-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d881-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d881-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d881-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
