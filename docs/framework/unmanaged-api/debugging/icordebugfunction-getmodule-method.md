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
ms.openlocfilehash: 5fad8b56b783748e23c8adc4aee0e1bf3450e243
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696130"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="238c6-102">ICorDebugFunction::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="238c6-102">ICorDebugFunction::GetModule Method</span></span>

<span data-ttu-id="238c6-103">이 함수가 정의 된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="238c6-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="238c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="238c6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="238c6-105">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="238c6-106">제한이 이 함수가 정의 된 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="238c6-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="238c6-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="238c6-107">Requirements</span></span>  

 <span data-ttu-id="238c6-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="238c6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="238c6-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="238c6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="238c6-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="238c6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="238c6-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="238c6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
