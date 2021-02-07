---
description: '자세히 알아보기: ICorDebugStepper:: SetRangeIL 메서드'
title: ICorDebugStepper::SetRangeIL 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
ms.openlocfilehash: 8bccaf8ba8e52a7fe94555fa99b1c3cf92842efe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717704"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="fa245-103">ICorDebugStepper::SetRangeIL 메서드</span><span class="sxs-lookup"><span data-stu-id="fa245-103">ICorDebugStepper::SetRangeIL Method</span></span>

<span data-ttu-id="fa245-104">[ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) 에 대 한 호출이 단계별로 진행 중인 메서드의 MSIL (Microsoft 중간 언어) 코드에 상대적인 인수 값을 전달 하는지 아니면 네이티브 코드에 상대적인 인수 값을 전달 하는지 여부를 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa245-104">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa245-105">구문</span><span class="sxs-lookup"><span data-stu-id="fa245-105">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa245-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fa245-106">Parameters</span></span>  

 `bIL`  
 <span data-ttu-id="fa245-107">진행 `true` 범위가 MSIL 코드를 기준으로 하도록 지정 하려면로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa245-107">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="fa245-108">`false`범위가 네이티브 코드를 기준으로 하도록 지정 하려면로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa245-108">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="fa245-109">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="fa245-109">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa245-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa245-110">Requirements</span></span>  

 <span data-ttu-id="fa245-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa245-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa245-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa245-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa245-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa245-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa245-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa245-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
