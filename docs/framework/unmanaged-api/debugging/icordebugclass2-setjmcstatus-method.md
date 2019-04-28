---
title: ICorDebugClass2::SetJMCStatus 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed6570e11008e52d4b1f97c2dc90e2ccbef2e35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750620"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="781cf-102">ICorDebugClass2::SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="781cf-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="781cf-103">클래스의 각 메서드의 경우 메서드는 사용자가 정의한 코드 있는지 여부를 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="781cf-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="781cf-104">구문</span><span class="sxs-lookup"><span data-stu-id="781cf-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="781cf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="781cf-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="781cf-106">[in] 로 `true` 메서드를 사용자 정의 임을 나타내려면로 고, 그렇지 않으면 코드 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="781cf-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="781cf-107">설명</span><span class="sxs-lookup"><span data-stu-id="781cf-107">Remarks</span></span>  
 <span data-ttu-id="781cf-108">내 코드만 (JMC) 스텝 퍼 사용자가 정의 되지 않은 코드를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="781cf-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="781cf-109">사용자 정의 코드 디버깅 가능한 코드가의 하위 집합 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="781cf-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="781cf-110">`SetJMCStatus` 다른 모든 메서드에 대 한 값을 성공적으로 설정 하는 경우에 모든 메서드에 대 한 값을 설정할 수 없는 경우 S_FALSE의 HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="781cf-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="781cf-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="781cf-111">Requirements</span></span>  
 <span data-ttu-id="781cf-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="781cf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="781cf-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="781cf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="781cf-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="781cf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="781cf-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="781cf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
