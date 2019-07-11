---
title: ICorDebugCode::GetFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10ab92c660353bea85bbd0918a25f716898ef837
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747527"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="2157d-102">ICorDebugCode::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="2157d-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="2157d-103">"ICorDebugFunction을"이 "ICorDebugCode"를 사용 하 여 연결을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2157d-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2157d-104">구문</span><span class="sxs-lookup"><span data-stu-id="2157d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2157d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2157d-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="2157d-106">[out] 함수 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2157d-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2157d-107">설명</span><span class="sxs-lookup"><span data-stu-id="2157d-107">Remarks</span></span>  
 <span data-ttu-id="2157d-108">`ICorDebugCode` 및 `ICorDebugFunction` 한 일 관계를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2157d-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2157d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2157d-109">Requirements</span></span>  
 <span data-ttu-id="2157d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2157d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2157d-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2157d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2157d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2157d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2157d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2157d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2157d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="2157d-114">See also</span></span>
