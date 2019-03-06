---
title: ICorDebugThread2::GetActiveFunctions 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed13f78d5a1f6d54b12c86613715f4878a521bfa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489932"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="6ae60-102">ICorDebugThread2::GetActiveFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="6ae60-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="6ae60-103">이 스레드의 프레임의 각 활성 함수에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ae60-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ae60-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ae60-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ae60-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ae60-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="6ae60-106">[in] `pFunctions` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae60-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="6ae60-107">[out] 반환 되는 개체의 수에 대 한 포인터를 `pFunctions` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae60-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="6ae60-108">반환 된 개체의 수는 관리 되는 스택 프레임의 수와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae60-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="6ae60-109">[out에서] 이 스레드의 프레임의 현재 함수에 대 한 정보를 포함 하는 각 COR_ACTIVE_FUNCTION 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae60-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="6ae60-110">첫 번째 요소의 리프 프레임과 등 백 스택의의 루트에 대해 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae60-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ae60-111">설명</span><span class="sxs-lookup"><span data-stu-id="6ae60-111">Remarks</span></span>  
 <span data-ttu-id="6ae60-112">하는 경우 `pFunctions` 가 입력 시 null `GetActiveFunctions` 스택에 있는 함수의 수만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae60-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="6ae60-113">즉, 하는 경우 `pFunctions` 가 입력 시 null `GetActiveFunctions` 값을 반환 에서만 `pcFunctions`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae60-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="6ae60-114">`GetActiveFunctions` 메서드는 최적화로 스택 추적의 프레임에서 동일한 정보를 가져오는 이며 했습니다 ICorDebugILFrame 개체에는 전체 스택 추적 프레임만 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae60-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ae60-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ae60-115">Requirements</span></span>  
 <span data-ttu-id="6ae60-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ae60-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ae60-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ae60-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ae60-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ae60-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ae60-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ae60-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
