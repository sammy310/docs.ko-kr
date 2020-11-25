---
title: ICorDebugManagedCallback::StepComplete 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
ms.openlocfilehash: 8de0858abe7db9ae1225f449083e417e13507b3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703044"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="1c31d-102">ICorDebugManagedCallback::StepComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="1c31d-102">ICorDebugManagedCallback::StepComplete Method</span></span>

<span data-ttu-id="1c31d-103">단계가 완료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1c31d-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c31d-104">구문</span><span class="sxs-lookup"><span data-stu-id="1c31d-104">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c31d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c31d-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="1c31d-106">진행 단계가 완료 된 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1c31d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="1c31d-107">진행 단계가 완료 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1c31d-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="1c31d-108">진행 코드 실행 단계를 나타내는 ICorDebugStepper 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1c31d-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="1c31d-109">진행 개별 단계의 결과를 나타내는 CorDebugStepReason 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1c31d-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c31d-110">설명</span><span class="sxs-lookup"><span data-stu-id="1c31d-110">Remarks</span></span>  

 <span data-ttu-id="1c31d-111">디버깅이 종료 되는 경우를 제외 하 고 원하는 경우 스텝 퍼를 사용 하 여 단계별 실행을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c31d-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c31d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c31d-112">Requirements</span></span>  

 <span data-ttu-id="1c31d-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c31d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c31d-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c31d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c31d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c31d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c31d-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c31d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c31d-117">참조</span><span class="sxs-lookup"><span data-stu-id="1c31d-117">See also</span></span>

- [<span data-ttu-id="1c31d-118">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c31d-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
