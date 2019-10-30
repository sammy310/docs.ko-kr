---
title: ICorDebugStepperEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type:
- apiref
ms.openlocfilehash: 11d9c7393827b613d49e23972b4896bfe657a544
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138984"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="e1fb4-102">ICorDebugStepperEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="e1fb4-102">ICorDebugStepperEnum::Next Method</span></span>
<span data-ttu-id="e1fb4-103">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 ICorDebugStepper 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb4-103">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1fb4-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1fb4-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1fb4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1fb4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e1fb4-106">진행 검색할 `ICorDebugStepper` 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb4-106">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="e1fb4-107">제한이 각각 `ICorDebugStepper` 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb4-107">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e1fb4-108">제한이 실제로 반환 된 `ICorDebugStepper` 인스턴스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb4-108">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="e1fb4-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1fb4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1fb4-110">Requirements</span></span>  
 <span data-ttu-id="e1fb4-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1fb4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1fb4-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1fb4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1fb4-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1fb4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1fb4-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1fb4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
