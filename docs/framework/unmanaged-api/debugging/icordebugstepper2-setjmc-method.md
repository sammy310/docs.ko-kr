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
ms.openlocfilehash: 6c076dd2912a22e4f9492492a2d7a9fb73db88e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139034"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="e5a03-102">ICorDebugStepper2::SetJMC 메서드</span><span class="sxs-lookup"><span data-stu-id="e5a03-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="e5a03-103">이 ICorDebugStepper 응용 프로그램 개발자가 작성 한 코드를 통해서만 단계별로 진행 하는지 여부를 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a03-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="e5a03-104">이 프로세스를 JMC (내 코드) 디버깅이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a03-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5a03-105">구문</span><span class="sxs-lookup"><span data-stu-id="e5a03-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5a03-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5a03-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="e5a03-107">진행 응용 프로그램 개발자가 작성 한 코드를 통해서만 단계별로 실행 되도록 `true`로 설정 합니다. 그렇지 않으면 `false`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a03-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5a03-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5a03-108">Requirements</span></span>  
 <span data-ttu-id="e5a03-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5a03-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5a03-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5a03-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5a03-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5a03-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5a03-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5a03-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
