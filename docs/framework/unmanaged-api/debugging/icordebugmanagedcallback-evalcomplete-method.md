---
description: '자세히 알아보기: ICorDebugManagedCallback:: EvalComplete 메서드'
title: ICorDebugManagedCallback::EvalComplete 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type:
- apiref
ms.openlocfilehash: 729b00bc630ef5d6e508b75bd6483580f1dd75b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791032"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="78603-103">ICorDebugManagedCallback::EvalComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="78603-103">ICorDebugManagedCallback::EvalComplete Method</span></span>

<span data-ttu-id="78603-104">평가가 완료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="78603-104">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78603-105">구문</span><span class="sxs-lookup"><span data-stu-id="78603-105">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78603-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="78603-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="78603-107">진행 평가가 수행 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="78603-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="78603-108">진행 계산이 수행 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="78603-108">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="78603-109">진행 계산을 수행 하는 코드를 나타내는 ICorDebugEval 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="78603-109">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78603-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78603-110">Requirements</span></span>  

 <span data-ttu-id="78603-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78603-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78603-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78603-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78603-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78603-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78603-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78603-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78603-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78603-115">See also</span></span>

- [<span data-ttu-id="78603-116">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78603-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
