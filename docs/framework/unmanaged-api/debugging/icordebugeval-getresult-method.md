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
ms.openlocfilehash: 52bfe669d3b078657916554255a11cecfc07d484
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085082"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="0dfc0-102">ICorDebugEval::GetResult 메서드</span><span class="sxs-lookup"><span data-stu-id="0dfc0-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="0dfc0-103">이 계산의 결과를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0dfc0-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dfc0-104">구문</span><span class="sxs-lookup"><span data-stu-id="0dfc0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dfc0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0dfc0-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="0dfc0-106">제한이 평가가 정상적으로 완료 되는 경우이 계산의 결과를 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfc0-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dfc0-107">주의</span><span class="sxs-lookup"><span data-stu-id="0dfc0-107">Remarks</span></span>  
 <span data-ttu-id="0dfc0-108">`GetResult` 메서드는 평가가 완료 된 후에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfc0-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="0dfc0-109">평가가 정상적으로 완료 되는 경우 `ppResult` 결과를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfc0-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="0dfc0-110">예외로 인해 종료 되 면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dfc0-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="0dfc0-111">새 개체에 대 한 평가 인 경우 결과는 새 개체에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfc0-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dfc0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0dfc0-112">Requirements</span></span>  
 <span data-ttu-id="0dfc0-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0dfc0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dfc0-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dfc0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dfc0-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dfc0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dfc0-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dfc0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
