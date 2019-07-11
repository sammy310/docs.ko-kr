---
title: ICorDebugFunction::GetModule 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6bfde8a934da857e580c603bd1c0115a04a4070
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754639"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="e98d1-102">ICorDebugFunction::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="e98d1-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="e98d1-103">이 함수는 정의 된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e98d1-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e98d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="e98d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e98d1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e98d1-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="e98d1-106">[out] 이 함수는 정의 된 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e98d1-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e98d1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e98d1-107">Requirements</span></span>  
 <span data-ttu-id="e98d1-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e98d1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e98d1-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e98d1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e98d1-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e98d1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e98d1-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e98d1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
