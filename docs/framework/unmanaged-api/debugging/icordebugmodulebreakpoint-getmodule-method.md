---
description: '자세히 알아보기: ICorDebugModuleBreakpoint:: GetModule 메서드'
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
ms.openlocfilehash: 3498f9d644d6195f2cd0f83d30417c447d200f3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790791"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="af15d-103">ICorDebugModuleBreakpoint::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="af15d-103">ICorDebugModuleBreakpoint::GetModule Method</span></span>

<span data-ttu-id="af15d-104">이 중단점이 설정 된 모듈을 참조 하는 "ICorDebugModule"에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af15d-104">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af15d-105">구문</span><span class="sxs-lookup"><span data-stu-id="af15d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af15d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af15d-106">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="af15d-107">제한이 `ICorDebugModule` 중단점이 설정 된 모듈을 참조 하는 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="af15d-107">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af15d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af15d-108">Requirements</span></span>  

 <span data-ttu-id="af15d-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af15d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af15d-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af15d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af15d-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af15d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af15d-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af15d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af15d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af15d-113">See also</span></span>
