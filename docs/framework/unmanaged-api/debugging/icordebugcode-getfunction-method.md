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
ms.openlocfilehash: 0104a52c3aa206f86daff30d9d16298e6beae324
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099458"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="251bd-102">ICorDebugCode::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="251bd-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="251bd-103">"ICorDebugFunction을"이 "ICorDebugCode"를 사용 하 여 연결을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="251bd-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="251bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="251bd-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="251bd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="251bd-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="251bd-106">[out] 함수 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="251bd-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="251bd-107">설명</span><span class="sxs-lookup"><span data-stu-id="251bd-107">Remarks</span></span>  
 <span data-ttu-id="251bd-108">`ICorDebugCode` 및 `ICorDebugFunction` 한 일 관계를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="251bd-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="251bd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="251bd-109">Requirements</span></span>  
 <span data-ttu-id="251bd-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="251bd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="251bd-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="251bd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="251bd-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="251bd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="251bd-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="251bd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="251bd-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="251bd-114">See also</span></span>
