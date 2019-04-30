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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d20c640d6a6a43b7bde4c7d46df470c7bc8c5aa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942513"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="542af-102">ICorDebugModule2::SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="542af-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="542af-103">이 ICorDebugModule2 제외한 지정 된 값의 모든 클래스의 모든 메서드의 코드 JMC (내) 상태를 설정 합니다 `pTokens` 반대 값으로 설정 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="542af-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="542af-104">구문</span><span class="sxs-lookup"><span data-stu-id="542af-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="542af-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="542af-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="542af-106">[in] 로 `true` 로 설정 하는 코드가 고 그렇지 않으면 디버깅 인 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="542af-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="542af-107">[in] `pTokens` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="542af-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="542af-108">[in] 배열을 `mdToken` 로 설정 된 JMC 상태에 있는 메서드를 참조 하는 각 값!`bIsJustMycode`합니다.</span><span class="sxs-lookup"><span data-stu-id="542af-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="542af-109">설명</span><span class="sxs-lookup"><span data-stu-id="542af-109">Remarks</span></span>  
 <span data-ttu-id="542af-110">에 지정 된 각 메서드의 JMC 상태를 `pTokens` 과 반대로 설정 되어 배열은 `bIsJustMycode` 값.</span><span class="sxs-lookup"><span data-stu-id="542af-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="542af-111">이 모듈의 다른 모든 메서드의 상태를로 `bIsJustMycode` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="542af-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="542af-112">`SetJMCStatus` 메서드는이 모듈의 모든 이전 JMC 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="542af-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="542af-113">`SetJMCStatus` 메서드는 모든 함수는 성공적으로 설정 된 경우 s_ok이 고, HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="542af-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="542af-114">표시 된 일부 함수는 경우 CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT를 반환 합니다 `true` 디버깅 가능 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="542af-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="542af-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="542af-115">Requirements</span></span>  
 <span data-ttu-id="542af-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="542af-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="542af-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="542af-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="542af-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="542af-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="542af-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="542af-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
