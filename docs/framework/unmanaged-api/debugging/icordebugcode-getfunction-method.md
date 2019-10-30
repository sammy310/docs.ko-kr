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
ms.openlocfilehash: 217ca0a850926e5f697340cece264c6ed442a9bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125638"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="374c7-102">ICorDebugCode::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="374c7-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="374c7-103">이 "ICorDebugCode"와 연결 된 "ICorDebugFunction"를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="374c7-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="374c7-104">구문</span><span class="sxs-lookup"><span data-stu-id="374c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="374c7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="374c7-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="374c7-106">제한이 함수 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="374c7-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="374c7-107">주의</span><span class="sxs-lookup"><span data-stu-id="374c7-107">Remarks</span></span>  
 <span data-ttu-id="374c7-108">`ICorDebugCode` 및 `ICorDebugFunction`는 일대일 관계를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="374c7-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="374c7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="374c7-109">Requirements</span></span>  
 <span data-ttu-id="374c7-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="374c7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="374c7-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="374c7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="374c7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="374c7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="374c7-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="374c7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
