---
description: '자세히 알아보기: ICorDebugBreakpointEnum:: Next 메서드'
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
ms.openlocfilehash: 966494bbabaca99b6b5168db6fb7616c15c537e1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711676"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="9f33f-103">ICorDebugBreakpointEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="9f33f-103">ICorDebugBreakpointEnum::Next Method</span></span>

<span data-ttu-id="9f33f-104">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 ICorDebugBreakpoint 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9f33f-104">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f33f-105">구문</span><span class="sxs-lookup"><span data-stu-id="9f33f-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f33f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9f33f-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="9f33f-107">진행 `ICorDebugBreakpoint` 검색할 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9f33f-107">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="9f33f-108">제한이 각각 중단점을 나타내는 개체를 가리키는 포인터의 배열입니다 `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="9f33f-108">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9f33f-109">제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugBreakpoint` 입니다.</span><span class="sxs-lookup"><span data-stu-id="9f33f-109">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="9f33f-110">이 일 경우이 값은 null 일 수 있습니다 `celt` .</span><span class="sxs-lookup"><span data-stu-id="9f33f-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f33f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9f33f-111">Requirements</span></span>  

 <span data-ttu-id="9f33f-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f33f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f33f-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f33f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f33f-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f33f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f33f-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f33f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
