---
title: ICorDebugModule2::SetJMCStatus 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: a0b70078dee88b270d8361aa9bddcb7d80df1db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129466"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="d7c9a-102">ICorDebugModule2::SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="d7c9a-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="d7c9a-103">이 ICorDebugModule2에 있는 모든 클래스의 모든 메서드에 대 한 내 코드만 (JMC) 상태를 지정 된 값으로 설정 합니다. 단, `pTokens` 배열의 경우에는 반대 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7c9a-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7c9a-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7c9a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7c9a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7c9a-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="d7c9a-106">진행 코드를 디버그할 수 있는 경우 `true`로 설정 합니다. 그렇지 않으면 `false`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7c9a-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="d7c9a-107">[in] `pTokens` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d7c9a-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="d7c9a-108">진행 각각 JMC 상태를로 설정 하는 메서드를 참조 하는 `mdToken` 값의 배열입니다.`bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="d7c9a-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7c9a-109">주의</span><span class="sxs-lookup"><span data-stu-id="d7c9a-109">Remarks</span></span>  
 <span data-ttu-id="d7c9a-110">`pTokens` 배열에 지정 된 각 메서드의 JMC 상태는 `bIsJustMycode` 값의 반대로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7c9a-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="d7c9a-111">이 모듈의 다른 모든 메서드 상태는 `bIsJustMycode` 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7c9a-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="d7c9a-112">`SetJMCStatus` 메서드는이 모듈에서 이전 JMC 설정을 모두 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="d7c9a-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="d7c9a-113">모든 함수가 성공적으로 설정 된 경우 `SetJMCStatus` 메서드는 S_OK HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7c9a-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="d7c9a-114">`true` 표시 된 일부 함수를 디버깅할 수 없는 경우 CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7c9a-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7c9a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7c9a-115">Requirements</span></span>  
 <span data-ttu-id="d7c9a-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7c9a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7c9a-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7c9a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7c9a-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7c9a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7c9a-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7c9a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
