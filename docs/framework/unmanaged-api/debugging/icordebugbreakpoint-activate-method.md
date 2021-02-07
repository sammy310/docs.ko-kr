---
description: '자세히 알아보기: ICorDebugBreakpoint:: Activate 메서드'
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
ms.openlocfilehash: 1a3613ae071b3fc6c4f1005eafd515946d6b2685
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711871"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="5a797-103">ICorDebugBreakpoint::Activate 메서드</span><span class="sxs-lookup"><span data-stu-id="5a797-103">ICorDebugBreakpoint::Activate Method</span></span>

<span data-ttu-id="5a797-104">이의 활성 상태를 설정 합니다 `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="5a797-104">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a797-105">구문</span><span class="sxs-lookup"><span data-stu-id="5a797-105">Syntax</span></span>  
  
```cpp  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a797-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a797-106">Parameters</span></span>  

 `bActive`  
 <span data-ttu-id="5a797-107">진행 상태를 활성으로 지정 하려면이 값을로 설정 하 `true` 고, 그렇지 않으면이 값을로 설정 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a797-107">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a797-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a797-108">Requirements</span></span>  

 <span data-ttu-id="5a797-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a797-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a797-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a797-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a797-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a797-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a797-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a797-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
