---
description: '자세히 알아보기: ICorDebugFunction2:: GetJMCStatus 메서드'
title: ICorDebugFunction2::GetJMCStatus 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 42c72256df57b96a52737f4a0e5e90d6ba5d4e0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692292"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="a2651-103">ICorDebugFunction2::GetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="a2651-103">ICorDebugFunction2::GetJMCStatus Method</span></span>

<span data-ttu-id="a2651-104">이 ICorDebugFunction2 개체가 나타내는 함수가 사용자 코드로 표시 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a2651-104">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2651-105">구문</span><span class="sxs-lookup"><span data-stu-id="a2651-105">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2651-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2651-106">Parameters</span></span>  

 `pbIsJustMyCode`  
 <span data-ttu-id="a2651-107">제한이 부울 값에 대 한 포인터입니다 `true` .이 함수가 사용자 코드로 표시 되 면이 고, 그렇지 않으면 값은 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a2651-107">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2651-108">설명</span><span class="sxs-lookup"><span data-stu-id="a2651-108">Remarks</span></span>  

 <span data-ttu-id="a2651-109">이가 나타내는 함수를 `ICorDebugFunction2` 디버그할 수 없는 경우 `pbIsJustMyCode` 는 항상 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a2651-109">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2651-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2651-110">Requirements</span></span>  

 <span data-ttu-id="a2651-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2651-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2651-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2651-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2651-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2651-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2651-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2651-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
