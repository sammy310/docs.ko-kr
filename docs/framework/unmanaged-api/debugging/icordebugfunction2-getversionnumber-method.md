---
title: ICorDebugFunction2::GetVersionNumber 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
ms.openlocfilehash: 5826297d8151cf05e1ec08acbf5c9cd381d2452b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137798"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="2223a-102">ICorDebugFunction2::GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="2223a-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="2223a-103">이 함수의 편집 하며 계속 하기 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2223a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2223a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2223a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2223a-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="2223a-106">제한이 이 ICorDebugFunction2 개체가 나타내는 함수의 버전 번호를 나타내는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2223a-107">주의</span><span class="sxs-lookup"><span data-stu-id="2223a-107">Remarks</span></span>  
 <span data-ttu-id="2223a-108">런타임은 디버그 세션 중에 각 모듈에 수행 된 편집 횟수를 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="2223a-109">함수의 버전 번호는 함수를 도입 하는 편집의 수보다 하나 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="2223a-110">함수의 원래 버전이 버전 1입니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-110">The function's original version is version 1.</span></span> <span data-ttu-id="2223a-111">이 모듈에 대해 [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) 가 호출 될 때마다 모듈의 숫자가 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="2223a-112">따라서 함수의 본문이 `GetVersionNumber` `ICorDebugModule2::ApplyChanges`에 대 한 첫 번째 및 세 번째 호출에서 대체 된 경우에는 해당 함수에 대 한 버전 1, 2 또는 4를 반환할 수 있지만 버전 3은 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="2223a-113">이 함수에는 버전 3이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="2223a-114">버전 번호는 각 모듈에 대해 개별적으로 추적 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="2223a-115">따라서 모듈 1에서 4 개의 편집을 수행 하 고 모듈 2에서는 지정 하지 않을 경우 모듈 1에서 다음 편집은 모듈 1의 모든 편집 된 함수에 버전 번호 6을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="2223a-116">동일한 편집이 모듈 2를 터치 하는 경우 모듈 2의 함수는 버전 번호 2를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="2223a-117">`GetVersionNumber` 메서드에서 얻은 버전 번호는 [ICorDebugFunction:: GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)에서 가져온 버전 보다 낮을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="2223a-118">[ICorDebugCode:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) 메서드는 `ICorDebugFunction2::GetVersionNumber`와 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2223a-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2223a-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2223a-119">Requirements</span></span>  
 <span data-ttu-id="2223a-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2223a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2223a-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2223a-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2223a-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2223a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2223a-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2223a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
