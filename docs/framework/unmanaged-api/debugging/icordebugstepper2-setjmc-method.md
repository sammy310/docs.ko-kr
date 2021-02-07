---
description: '자세히 알아보기: ICorDebugStepper2:: SetJMC 메서드'
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
ms.openlocfilehash: 07178ab90bb392e64c9d8a8fddf961efbb268002
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717539"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="5b655-103">ICorDebugStepper2::SetJMC 메서드</span><span class="sxs-lookup"><span data-stu-id="5b655-103">ICorDebugStepper2::SetJMC Method</span></span>

<span data-ttu-id="5b655-104">이 ICorDebugStepper 응용 프로그램 개발자가 작성 한 코드를 통해서만 단계별로 진행 하는지 여부를 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b655-104">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="5b655-105">이 프로세스를 JMC (내 코드) 디버깅이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b655-105">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b655-106">구문</span><span class="sxs-lookup"><span data-stu-id="5b655-106">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b655-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b655-107">Parameters</span></span>  

 `fIsJMCStepper`  
 <span data-ttu-id="5b655-108">진행 `true` 응용 프로그램의 개발자가 작성 한 코드를 통해서만 단계별로 실행 하려면로 설정 하 고, 그렇지 않으면로 설정 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b655-108">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b655-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b655-109">Requirements</span></span>  

 <span data-ttu-id="5b655-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b655-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b655-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b655-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b655-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b655-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b655-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b655-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
