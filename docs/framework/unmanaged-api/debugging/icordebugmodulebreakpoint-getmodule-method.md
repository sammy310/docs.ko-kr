---
title: ICorDebugModuleBreakpoint::GetModule 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type:
- apiref
ms.openlocfilehash: b6363ef901d5297862ca46e685bb783aaaeb4123
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709624"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="7c5d7-102">ICorDebugModuleBreakpoint::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="7c5d7-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>

<span data-ttu-id="7c5d7-103">이 중단점이 설정 된 모듈을 참조 하는 "ICorDebugModule"에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c5d7-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c5d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c5d7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c5d7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c5d7-105">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="7c5d7-106">제한이 `ICorDebugModule` 중단점이 설정 된 모듈을 참조 하는 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5d7-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c5d7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c5d7-107">Requirements</span></span>  

 <span data-ttu-id="7c5d7-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c5d7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c5d7-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c5d7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c5d7-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c5d7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c5d7-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c5d7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c5d7-112">참조</span><span class="sxs-lookup"><span data-stu-id="7c5d7-112">See also</span></span>
