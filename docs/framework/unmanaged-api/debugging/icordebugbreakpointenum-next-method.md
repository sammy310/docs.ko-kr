---
title: ICorDebugBreakpointEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
ms.openlocfilehash: d29576c6f073f1d0e8e0aea417fc38c09a8327c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122740"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="4daf3-102">ICorDebugBreakpointEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="4daf3-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="4daf3-103">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 ICorDebugBreakpoint 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4daf3-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4daf3-104">구문</span><span class="sxs-lookup"><span data-stu-id="4daf3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4daf3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4daf3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4daf3-106">진행 검색할 `ICorDebugBreakpoint` 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4daf3-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="4daf3-107">제한이 각각 중단점을 나타내는 `ICorDebugBreakpoint` 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4daf3-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="4daf3-108">제한이 실제로 반환 된 `ICorDebugBreakpoint` 인스턴스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4daf3-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="4daf3-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4daf3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4daf3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4daf3-110">Requirements</span></span>  
 <span data-ttu-id="4daf3-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4daf3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4daf3-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4daf3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4daf3-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4daf3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4daf3-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4daf3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
