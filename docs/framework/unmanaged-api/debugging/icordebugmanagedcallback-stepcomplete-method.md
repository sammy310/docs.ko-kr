---
description: '자세히 알아보기: ICorDebugManagedCallback:: Stcomplete 메서드'
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
ms.openlocfilehash: 653abee26f09ac8877be9fa4183763739845666a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660364"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="0911a-103">ICorDebugManagedCallback::StepComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="0911a-103">ICorDebugManagedCallback::StepComplete Method</span></span>

<span data-ttu-id="0911a-104">단계가 완료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0911a-104">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0911a-105">구문</span><span class="sxs-lookup"><span data-stu-id="0911a-105">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0911a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0911a-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="0911a-107">진행 단계가 완료 된 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0911a-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="0911a-108">진행 단계가 완료 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0911a-108">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="0911a-109">진행 코드 실행 단계를 나타내는 ICorDebugStepper 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0911a-109">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="0911a-110">진행 개별 단계의 결과를 나타내는 CorDebugStepReason 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0911a-110">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0911a-111">설명</span><span class="sxs-lookup"><span data-stu-id="0911a-111">Remarks</span></span>  

 <span data-ttu-id="0911a-112">디버깅이 종료 되는 경우를 제외 하 고 원하는 경우 스텝 퍼를 사용 하 여 단계별 실행을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0911a-112">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0911a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0911a-113">Requirements</span></span>  

 <span data-ttu-id="0911a-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0911a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0911a-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0911a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0911a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0911a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0911a-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0911a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0911a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0911a-118">See also</span></span>

- [<span data-ttu-id="0911a-119">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0911a-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
