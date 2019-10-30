---
title: ICorDebugBreakpoint::Activate 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
ms.openlocfilehash: 50794e96484432c8b7c203f6b8caa60130068a8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122782"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="3b10a-102">ICorDebugBreakpoint::Activate 메서드</span><span class="sxs-lookup"><span data-stu-id="3b10a-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="3b10a-103">이 `ICorDebugBreakpoint`의 활성 상태를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b10a-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b10a-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b10a-104">Syntax</span></span>  
  
```cpp  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b10a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b10a-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="3b10a-106">진행 상태를 활성으로 지정 하려면이 값을 `true` 설정 합니다. 그렇지 않으면이 값을 `false`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b10a-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b10a-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b10a-107">Requirements</span></span>  
 <span data-ttu-id="3b10a-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b10a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b10a-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b10a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b10a-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b10a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b10a-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b10a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
