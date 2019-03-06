---
title: ICorDebugAppDomain::EnumerateSteppers 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateSteppers
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d326c801ed17fa6fe79f9e464e64844d0016e572
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489360"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="3aa7e-102">ICorDebugAppDomain::EnumerateSteppers 메서드</span><span class="sxs-lookup"><span data-stu-id="3aa7e-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="3aa7e-103">응용 프로그램 도메인에서 모든 활성 스텝 퍼에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3aa7e-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aa7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="3aa7e-104">Syntax</span></span>  
  
```  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3aa7e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3aa7e-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="3aa7e-106">[out] 응용 프로그램 도메인에서 모든 활성 스텝 퍼에 대 한 열거자는 ICorDebugStepperEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa7e-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aa7e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3aa7e-107">Requirements</span></span>  
 <span data-ttu-id="3aa7e-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa7e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aa7e-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3aa7e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3aa7e-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3aa7e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3aa7e-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3aa7e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
