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
ms.openlocfilehash: c5d8168649f6a0c75844da0ee68bf3782efc9024
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483867"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="baea8-102">ICorDebugCode::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="baea8-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="baea8-103">"ICorDebugFunction을"이 "ICorDebugCode"를 사용 하 여 연결을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="baea8-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baea8-104">구문</span><span class="sxs-lookup"><span data-stu-id="baea8-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baea8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="baea8-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="baea8-106">[out] 함수 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="baea8-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baea8-107">설명</span><span class="sxs-lookup"><span data-stu-id="baea8-107">Remarks</span></span>  
 <span data-ttu-id="baea8-108">`ICorDebugCode` 및 `ICorDebugFunction` 한 일 관계를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="baea8-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baea8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="baea8-109">Requirements</span></span>  
 <span data-ttu-id="baea8-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="baea8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baea8-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="baea8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="baea8-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baea8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baea8-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baea8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baea8-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="baea8-114">See also</span></span>

