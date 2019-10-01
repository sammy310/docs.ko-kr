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
ms.openlocfilehash: 825840536968562a53d9e05b8a4628a1df79407d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700828"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="1fcae-102">ICorDebugCode::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="1fcae-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="1fcae-103">이 "ICorDebugCode"와 연결 된 "ICorDebugFunction"를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1fcae-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fcae-104">구문</span><span class="sxs-lookup"><span data-stu-id="1fcae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fcae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1fcae-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="1fcae-106">제한이 함수 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1fcae-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fcae-107">설명</span><span class="sxs-lookup"><span data-stu-id="1fcae-107">Remarks</span></span>  
 <span data-ttu-id="1fcae-108">`ICorDebugCode` 및 `ICorDebugFunction`은 일 대 일 관계를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fcae-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fcae-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1fcae-109">Requirements</span></span>  
 <span data-ttu-id="1fcae-110">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1fcae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fcae-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fcae-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fcae-112">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fcae-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fcae-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fcae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
