---
title: ICorDebugFunction::CreateBreakpoint 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695ce7f25813a191c74bec6563fc7f8ae8d1143d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496120"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="b7766-102">ICorDebugFunction::CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="b7766-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="b7766-103">이 함수의 시작 부분에 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7766-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7766-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7766-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7766-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7766-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="b7766-106">[out] 함수에 대 한 새 중단점을 나타내는 ICorDebugFunctionBreakpoint 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b7766-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7766-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7766-107">Requirements</span></span>  
 <span data-ttu-id="b7766-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7766-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7766-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7766-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7766-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7766-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7766-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7766-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
