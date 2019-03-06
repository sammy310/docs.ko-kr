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
ms.openlocfilehash: 1cefe84c482df3b20b5939e031ad76647f295d3e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484626"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="15627-102">ICorDebugFunction::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="15627-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="15627-103">이 함수는 정의 된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="15627-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15627-104">구문</span><span class="sxs-lookup"><span data-stu-id="15627-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15627-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15627-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="15627-106">[out] 이 함수는 정의 된 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="15627-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15627-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15627-107">Requirements</span></span>  
 <span data-ttu-id="15627-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="15627-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15627-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15627-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15627-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15627-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15627-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15627-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
