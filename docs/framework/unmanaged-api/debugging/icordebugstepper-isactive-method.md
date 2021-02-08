---
description: '자세히 알아보기: ICorDebugStepper:: IsActive 메서드'
title: ICorDebugStepper::IsActive 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: 7ef937ac3c1e6f3ad9ad83b5fa84382cac3ac9c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803570"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="cd870-103">ICorDebugStepper::IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="cd870-103">ICorDebugStepper::IsActive Method</span></span>

<span data-ttu-id="cd870-104">이 ICorDebugStepper 현재 단계를 실행 하 고 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd870-104">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd870-105">구문</span><span class="sxs-lookup"><span data-stu-id="cd870-105">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd870-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd870-106">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="cd870-107">제한이 `true` 스텝 퍼가 현재 단계를 실행 하 고 있으면를 반환 하 고, 그렇지 않으면를 반환 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd870-107">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd870-108">설명</span><span class="sxs-lookup"><span data-stu-id="cd870-108">Remarks</span></span>  

 <span data-ttu-id="cd870-109">모든 단계 동작은 디버거가 [ICorDebugManagedCallback:: Stcomplete](icordebugmanagedcallback-stepcomplete-method.md) 호출을 받을 때까지 활성 상태로 유지 되어 자동으로 스텝 퍼를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd870-109">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="cd870-110">콜백 조건에 도달 하기 전에 [ICorDebugStepper::D eactivate](icordebugstepper-deactivate-method.md) 를 호출 하 여 스텝 퍼를 중간에 비활성화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd870-110">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd870-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd870-111">Requirements</span></span>  

 <span data-ttu-id="cd870-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd870-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd870-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd870-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd870-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd870-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd870-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd870-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
