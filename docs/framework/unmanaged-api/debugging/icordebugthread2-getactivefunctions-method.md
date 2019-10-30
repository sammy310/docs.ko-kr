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
ms.openlocfilehash: 9b9a301714ea60b4e3220eb75721e56e39bd9659
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139938"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="164f1-102">ICorDebugThread2::GetActiveFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="164f1-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="164f1-103">이 스레드의 각 프레임에서 활성 함수에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="164f1-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="164f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="164f1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="164f1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="164f1-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="164f1-106">[in] `pFunctions` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="164f1-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="164f1-107">제한이 `pFunctions` 배열에 반환 되는 개체 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="164f1-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="164f1-108">반환 되는 개체의 수는 스택의 관리 되는 프레임 수와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="164f1-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="164f1-109">[in, out] 각각이 스레드의 프레임에 있는 활성 함수에 대 한 정보를 포함 하는 COR_ACTIVE_FUNCTION 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="164f1-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="164f1-110">첫 번째 요소는 리프 프레임에 사용 되며, 따라서 스택의 루트로 다시 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="164f1-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="164f1-111">주의</span><span class="sxs-lookup"><span data-stu-id="164f1-111">Remarks</span></span>  
 <span data-ttu-id="164f1-112">입력 시 `pFunctions`가 null 이면 `GetActiveFunctions`는 스택에 있는 함수 수만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="164f1-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="164f1-113">즉, 입력에서 `pFunctions`가 null 인 경우에는 `GetActiveFunctions` `pcFunctions`에서만 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="164f1-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="164f1-114">`GetActiveFunctions` 메서드는 스택 추적의 프레임에서 동일한 정보를 가져오는 것 보다 최적화 된 것 이며 전체 스택 추적에 ICorDebugILFrame 개체가 있는 프레임만 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="164f1-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="164f1-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="164f1-115">Requirements</span></span>  
 <span data-ttu-id="164f1-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="164f1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="164f1-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="164f1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="164f1-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="164f1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="164f1-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="164f1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
