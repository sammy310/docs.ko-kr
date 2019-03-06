---
title: ICorDebugStepper2::SetJMC 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 129bf04a097b2019b080f813bf049d41b501f8fd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474217"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="ceb5f-102">ICorDebugStepper2::SetJMC 메서드</span><span class="sxs-lookup"><span data-stu-id="ceb5f-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="ceb5f-103">응용 프로그램의 개발자가 작성 된 코드를 통해서만이 ICorDebugStepper 단계 여부를 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb5f-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="ceb5f-104">이 프로세스는으로 내 코드만 (JMC) 디버깅 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb5f-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb5f-105">구문</span><span class="sxs-lookup"><span data-stu-id="ceb5f-105">Syntax</span></span>  
  
```  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ceb5f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ceb5f-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="ceb5f-107">[in] 로 `true` 코드는 응용 프로그램의 개발자가 작성 한이 고, 그렇지로 단계별로 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb5f-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceb5f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ceb5f-108">Requirements</span></span>  
 <span data-ttu-id="ceb5f-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ceb5f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceb5f-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ceb5f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ceb5f-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ceb5f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ceb5f-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceb5f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
