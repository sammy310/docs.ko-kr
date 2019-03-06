---
title: ICorDebugEval::GetResult 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8e7fcb4f44d6bdf6f18c93b1046b549331621a4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470798"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="67e1e-102">ICorDebugEval::GetResult 메서드</span><span class="sxs-lookup"><span data-stu-id="67e1e-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="67e1e-103">이 평가의 결과를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="67e1e-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e1e-104">구문</span><span class="sxs-lookup"><span data-stu-id="67e1e-104">Syntax</span></span>  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67e1e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="67e1e-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="67e1e-106">[out] 평가 정상적으로 완료 되 면이 평가의 결과 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="67e1e-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67e1e-107">설명</span><span class="sxs-lookup"><span data-stu-id="67e1e-107">Remarks</span></span>  
 <span data-ttu-id="67e1e-108">`GetResult` 메서드는 계산이 완료 된 후에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="67e1e-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="67e1e-109">평가 일반적으로 완료 되 면 `ppResult` 결과 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67e1e-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="67e1e-110">예외와 함께 종료 될 경우 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e1e-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="67e1e-111">새 개체에 대 한 평가 되었으면 결과 새 개체에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="67e1e-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67e1e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="67e1e-112">Requirements</span></span>  
 <span data-ttu-id="67e1e-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67e1e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67e1e-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67e1e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67e1e-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67e1e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67e1e-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67e1e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
