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
ms.openlocfilehash: 41ad10fecca2ba1831d9e0d1120d3d1be0be92ad
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212960"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="6352e-102">ICorDebugFunction::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="6352e-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="6352e-103">이 함수가 정의 된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6352e-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6352e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6352e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6352e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6352e-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="6352e-106">제한이 이 함수가 정의 된 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6352e-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6352e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6352e-107">Requirements</span></span>  
 <span data-ttu-id="6352e-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6352e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6352e-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6352e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6352e-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6352e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6352e-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6352e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
