---
description: '자세히 알아보기: ICorDebugFunction2:: SetJMCStatus 메서드'
title: ICorDebugFunction2::SetJMCStatus 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
ms.openlocfilehash: d2df9d47808b0220a91bd344e7600f8d16eccdb4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692188"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="a3ad6-103">ICorDebugFunction2::SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="a3ad6-103">ICorDebugFunction2::SetJMCStatus Method</span></span>

<span data-ttu-id="a3ad6-104">내 코드만 단계별 실행을 위해이 ICorDebugFunction2가 나타내는 함수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ad6-104">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3ad6-105">구문</span><span class="sxs-lookup"><span data-stu-id="a3ad6-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3ad6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3ad6-106">Parameters</span></span>  

 `bIsJustMyCode`  
 <span data-ttu-id="a3ad6-107">진행 함수를 `true` 사용자 코드로 표시 하려면로 설정 하 고 그렇지 않으면로 설정 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ad6-107">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="a3ad6-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="a3ad6-108">Return Values</span></span>  
  
|<span data-ttu-id="a3ad6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3ad6-109">HRESULT</span></span>|<span data-ttu-id="a3ad6-110">설명</span><span class="sxs-lookup"><span data-stu-id="a3ad6-110">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a3ad6-111">함수가로 표시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ad6-111">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="a3ad6-112">디버깅할 수 없으므로 함수를 사용자 코드로 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ad6-112">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3ad6-113">설명</span><span class="sxs-lookup"><span data-stu-id="a3ad6-113">Remarks</span></span>  

 <span data-ttu-id="a3ad6-114">내 코드만 스텝 퍼는 사용자가 아닌 코드를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="a3ad6-114">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="a3ad6-115">사용자 코드는 디버깅 가능한 코드의 하위 집합 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ad6-115">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3ad6-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3ad6-116">Requirements</span></span>  

 <span data-ttu-id="a3ad6-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3ad6-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3ad6-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3ad6-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3ad6-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3ad6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3ad6-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3ad6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
