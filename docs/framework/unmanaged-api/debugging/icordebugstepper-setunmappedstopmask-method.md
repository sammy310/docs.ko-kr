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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da799b0d4f4e5e4b281445baa35d95f992ba0b63
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474958"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="a2b46-102">ICorDebugStepper::SetUnmappedStopMask 메서드</span><span class="sxs-lookup"><span data-stu-id="a2b46-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="a2b46-103">매핑되지 않은 코드 실행을 중지할의 형식을 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b46-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2b46-104">구문</span><span class="sxs-lookup"><span data-stu-id="a2b46-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2b46-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2b46-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="a2b46-106">[in] 디버거는 실행을 중단 하는 데는 비관리 코드의 형식을 지정 하는 CorDebugUnmappedStop 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a2b46-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="a2b46-107">기본값은 STOP_OTHER_UNMAPPED 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b46-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="a2b46-108">값 STOP_UNMANAGED interop 디버깅만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b46-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2b46-109">설명</span><span class="sxs-lookup"><span data-stu-id="a2b46-109">Remarks</span></span>  
 <span data-ttu-id="a2b46-110">비관리 코드의 해당 형식을 지정 하는 플래그를 설정한; 경우 실행 중단 디버거에서 MSIL (Microsoft intermediate language)에 해당 매핑이 없는-just-in-time (JIT) 컴파일에서 찾으면 그렇지 않으면가 계속 투명 하 게 단계별로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b46-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="a2b46-111">디버거를 사용 하지 않는 스텝 메서드를 입력 하는 경우 다음 않습니다 반드시 실행 매핑되지 않은 코드.</span><span class="sxs-lookup"><span data-stu-id="a2b46-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2b46-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2b46-112">Requirements</span></span>  
 <span data-ttu-id="a2b46-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a2b46-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2b46-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2b46-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2b46-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2b46-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2b46-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2b46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
