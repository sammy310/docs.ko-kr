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
ms.openlocfilehash: fd9243d9e0c12b572613694538661fd553e8a487
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715929"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="a4e06-102">ICorDebugAppDomain::EnumerateSteppers 메서드</span><span class="sxs-lookup"><span data-stu-id="a4e06-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>

<span data-ttu-id="a4e06-103">응용 프로그램 도메인의 모든 활성 steppers에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4e06-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4e06-104">구문</span><span class="sxs-lookup"><span data-stu-id="a4e06-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4e06-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4e06-105">Parameters</span></span>  

 `ppSteppers`  
 <span data-ttu-id="a4e06-106">제한이 응용 프로그램 도메인의 모든 활성 steppers 열거자 인 ICorDebugStepperEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e06-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4e06-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4e06-107">Requirements</span></span>  

 <span data-ttu-id="a4e06-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e06-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4e06-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4e06-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4e06-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4e06-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4e06-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4e06-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
