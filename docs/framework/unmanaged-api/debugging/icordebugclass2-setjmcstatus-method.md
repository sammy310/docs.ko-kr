---
title: ICorDebugClass2::SetJMCStatus 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: 9fb2f960098e970b4d3d9f0be499f4d9fda6558e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893903"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="27e70-102">ICorDebugClass2::SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="27e70-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="27e70-103">클래스의 각 메서드에 대해 메서드가 사용자 정의 코드 인지 여부를 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e70-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27e70-104">구문</span><span class="sxs-lookup"><span data-stu-id="27e70-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27e70-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27e70-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="27e70-106">진행 `true` 메서드가 사용자 정의 코드 임을 나타내려면로 설정 합니다. 그렇지 않으면를로 `false`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e70-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27e70-107">설명</span><span class="sxs-lookup"><span data-stu-id="27e70-107">Remarks</span></span>  
 <span data-ttu-id="27e70-108">내 코드만 (JMC) 스텝 퍼는 사용자가 정의 하지 않은 코드를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="27e70-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="27e70-109">사용자 정의 코드는 디버깅 가능한 코드의 하위 집합 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e70-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="27e70-110">`SetJMCStatus`모든 메서드에 대 한 값을 설정 하는 데 실패 한 경우에도 S_FALSE HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e70-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27e70-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27e70-111">Requirements</span></span>  
 <span data-ttu-id="27e70-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27e70-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27e70-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27e70-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27e70-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27e70-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27e70-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27e70-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
