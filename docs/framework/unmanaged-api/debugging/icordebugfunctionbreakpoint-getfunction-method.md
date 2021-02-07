---
description: '자세히 알아보기: ICorDebugFunctionBreakpoint:: GetFunction 메서드'
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
ms.openlocfilehash: 1e407acda81e5e6397da003a9b91a48d4d171e5d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754097"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="1eec1-103">ICorDebugFunctionBreakpoint::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="1eec1-103">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>

<span data-ttu-id="1eec1-104">중단점이 설정 된 함수를 참조 하는 ICorDebugFunction에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1eec1-104">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eec1-105">구문</span><span class="sxs-lookup"><span data-stu-id="1eec1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eec1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1eec1-106">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="1eec1-107">제한이 중단점이 설정 된 함수의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1eec1-107">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eec1-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1eec1-108">Requirements</span></span>  

 <span data-ttu-id="1eec1-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eec1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eec1-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1eec1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1eec1-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1eec1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1eec1-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eec1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
