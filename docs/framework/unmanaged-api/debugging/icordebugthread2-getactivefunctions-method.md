---
description: '자세히 알아보기: ICorDebugThread2:: GetActiveFunctions 메서드'
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
ms.openlocfilehash: 841e8ff17f15cfb14e1c1bf65c651a5177db2eaa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658765"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="ae478-103">ICorDebugThread2::GetActiveFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="ae478-103">ICorDebugThread2::GetActiveFunctions Method</span></span>

<span data-ttu-id="ae478-104">이 스레드의 각 프레임에서 활성 함수에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae478-104">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae478-105">구문</span><span class="sxs-lookup"><span data-stu-id="ae478-105">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae478-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae478-106">Parameters</span></span>  

 `cFunctions`  
 <span data-ttu-id="ae478-107">[in] `pFunctions` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ae478-107">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="ae478-108">제한이 배열에 반환 되는 개체 수에 대 한 포인터 `pFunctions` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ae478-108">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="ae478-109">반환 되는 개체의 수는 스택의 관리 되는 프레임 수와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ae478-109">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="ae478-110">[in, out] 각각이 스레드의 프레임에 있는 활성 함수에 대 한 정보를 포함 하는 COR_ACTIVE_FUNCTION 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ae478-110">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="ae478-111">첫 번째 요소는 리프 프레임에 사용 되며, 따라서 스택의 루트로 다시 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae478-111">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae478-112">설명</span><span class="sxs-lookup"><span data-stu-id="ae478-112">Remarks</span></span>  

 <span data-ttu-id="ae478-113">`pFunctions`입력 시가 null 이면는 `GetActiveFunctions` 스택에 있는 함수 수만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae478-113">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="ae478-114">즉, `pFunctions` 입력 시가 null 인 경우 `GetActiveFunctions` 에만 값을 반환 `pcFunctions` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae478-114">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="ae478-115">`GetActiveFunctions`메서드는 스택 추적의 프레임에서 동일한 정보를 가져오는 것 보다 최적화 된 것 이며 전체 스택 추적에 ICorDebugILFrame 개체가 있는 프레임만 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae478-115">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae478-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae478-116">Requirements</span></span>  

 <span data-ttu-id="ae478-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae478-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae478-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae478-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae478-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae478-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae478-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae478-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
