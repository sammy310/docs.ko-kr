---
title: ICorDebugStepper::SetUnmappedStopMask 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
ms.openlocfilehash: 50fad8b38a6b33d0ddbb2f0f20676296c3d66737
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698749"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="5bd4d-102">ICorDebugStepper::SetUnmappedStopMask 메서드</span><span class="sxs-lookup"><span data-stu-id="5bd4d-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>

<span data-ttu-id="5bd4d-103">실행이 중단 되는 매핑되지 않은 코드의 형식을 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd4d-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bd4d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5bd4d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bd4d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5bd4d-105">Parameters</span></span>  

 `mask`  
 <span data-ttu-id="5bd4d-106">진행 디버거가 실행을 중단 하는 매핑되지 않은 코드의 형식을 지정 하는 CorDebugUnmappedStop 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd4d-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="5bd4d-107">기본값은 STOP_OTHER_UNMAPPED입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd4d-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="5bd4d-108">STOP_UNMANAGED 값은 interop 디버깅에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bd4d-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bd4d-109">설명</span><span class="sxs-lookup"><span data-stu-id="5bd4d-109">Remarks</span></span>  

 <span data-ttu-id="5bd4d-110">디버거가 MSIL (Microsoft 중간 언어)에 대 한 해당 매핑이 없는 JIT (just-in-time) 컴파일을 찾은 경우 매핑되지 않은 코드 형식을 지정 하는 플래그가 설정 되 면 실행이 중단 됩니다. 그렇지 않은 경우 단계별 실행은 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bd4d-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="5bd4d-111">디버거가 메서드를 시작 하는 데 스텝 퍼를 사용 하지 않는 경우 매핑되지 않은 코드를 한 단계씩 실행 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bd4d-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bd4d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bd4d-112">Requirements</span></span>  

 <span data-ttu-id="5bd4d-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bd4d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bd4d-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bd4d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bd4d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bd4d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bd4d-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bd4d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
