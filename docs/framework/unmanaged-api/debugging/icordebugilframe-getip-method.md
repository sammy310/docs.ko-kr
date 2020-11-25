---
title: ICorDebugILFrame::GetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
ms.openlocfilehash: 314d2a06c8e246a42b315690dc9fe4b507db285a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703176"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="6b614-102">ICorDebugILFrame::GetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="6b614-102">ICorDebugILFrame::GetIP Method</span></span>

<span data-ttu-id="6b614-103">명령 포인터의 값과 명령 포인터의 값을 가져오는 방법을 설명 하는 비트 조합 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6b614-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b614-104">구문</span><span class="sxs-lookup"><span data-stu-id="6b614-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b614-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b614-105">Parameters</span></span>  

 `pnOffset`  
 <span data-ttu-id="6b614-106">제한이 명령 포인터의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6b614-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="6b614-107">제한이 명령 포인터의 값을 가져오는 방법을 설명 하는 CorDebugMappingResult 열거형 값의 비트 조합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6b614-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b614-108">설명</span><span class="sxs-lookup"><span data-stu-id="6b614-108">Remarks</span></span>  

 <span data-ttu-id="6b614-109">명령 포인터의 값은 함수의 MSIL (Microsoft 중간 언어) 코드에 대 한 스택 프레임의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="6b614-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="6b614-110">스택 프레임이 활성 상태인 경우이 주소는 다음에 실행할 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="6b614-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="6b614-111">스택 프레임이 활성 상태가 아닌 경우이 주소는 스택 프레임이 다시 활성화 될 때 실행할 다음 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="6b614-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="6b614-112">이 프레임이 JIT (just-in-time) 컴파일된 프레임 인 경우 실제 네이티브 명령 포인터에서 역방향으로 매핑하여 명령 포인터의 값이 결정 되므로 값은 근사값이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b614-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b614-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b614-113">Requirements</span></span>  

 <span data-ttu-id="6b614-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b614-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b614-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b614-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b614-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b614-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b614-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b614-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
