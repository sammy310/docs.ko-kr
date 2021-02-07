---
description: '자세히 알아보기: ICorDebugStepperEnum:: Next 메서드'
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
ms.openlocfilehash: e0c17fbc570d5ea8a4a56c89a5a2c855ed045bd7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717461"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="8f295-103">ICorDebugStepperEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="8f295-103">ICorDebugStepperEnum::Next Method</span></span>

<span data-ttu-id="8f295-104">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 ICorDebugStepper 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f295-104">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f295-105">구문</span><span class="sxs-lookup"><span data-stu-id="8f295-105">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f295-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f295-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="8f295-107">진행 `ICorDebugStepper` 검색할 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f295-107">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="8f295-108">제한이 각각 개체를 가리키는 포인터의 배열입니다 `ICorDebugStepper` .</span><span class="sxs-lookup"><span data-stu-id="8f295-108">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8f295-109">제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugStepper` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8f295-109">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="8f295-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="8f295-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f295-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f295-111">Requirements</span></span>  

 <span data-ttu-id="8f295-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f295-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f295-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f295-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f295-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f295-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f295-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f295-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
