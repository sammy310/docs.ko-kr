---
title: ICorDebugFunctionBreakpoint::GetFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetFunction
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetFunction method [.NET Framework debugging]
- GetFunction method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 2a62dae5-dd8a-4696-b817-0e1e586c24a0
topic_type:
- apiref
ms.openlocfilehash: 0b53c80157bfd99a766eb691e8a8a2e6b9659a95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137755"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="c4f2d-102">ICorDebugFunctionBreakpoint::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="c4f2d-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="c4f2d-103">중단점이 설정 된 함수를 참조 하는 ICorDebugFunction에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4f2d-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4f2d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4f2d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c4f2d-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="c4f2d-106">제한이 중단점이 설정 된 함수의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4f2d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4f2d-107">Requirements</span></span>  
 <span data-ttu-id="c4f2d-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4f2d-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4f2d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4f2d-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4f2d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4f2d-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4f2d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
