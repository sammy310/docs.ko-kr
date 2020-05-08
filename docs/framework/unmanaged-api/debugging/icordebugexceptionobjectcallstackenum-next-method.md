---
title: ICorDebugExceptionObjectCallStackEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
ms.openlocfilehash: 6fce9f61e222d0fc1763495de162a94a7fc22689
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975981"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="d2a0e-102">ICorDebugExceptionObjectCallStackEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="d2a0e-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="d2a0e-103">예외 개체의 호출 스택 정보를 포함 하는 지정 된 수의 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d2a0e-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2a0e-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2a0e-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2a0e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2a0e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d2a0e-106">진행 검색할 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a0e-106">[in] The number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="d2a0e-107">제한이 각가 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a0e-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d2a0e-108">제한이 실제로 반환 된 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 인스턴스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a0e-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2a0e-109">설명</span><span class="sxs-lookup"><span data-stu-id="d2a0e-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2a0e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2a0e-110">Requirements</span></span>  
 <span data-ttu-id="d2a0e-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a0e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2a0e-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2a0e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2a0e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2a0e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2a0e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2a0e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a0e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2a0e-115">See also</span></span>

- [<span data-ttu-id="d2a0e-116">ICorDebugExceptionObjectCallStackEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2a0e-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="d2a0e-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2a0e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
