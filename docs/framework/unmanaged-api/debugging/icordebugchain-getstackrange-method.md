---
title: ICorDebugChain::GetStackRange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: 40ecc183c32500ad9e88ceb1bfc0528d717430e8
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894462"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="29ea0-102">ICorDebugChain::GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="29ea0-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="29ea0-103">이 체인의 스택 세그먼트에 대 한 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="29ea0-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29ea0-104">구문</span><span class="sxs-lookup"><span data-stu-id="29ea0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29ea0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29ea0-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="29ea0-106">제한이 스택 세그먼트의 시작 `CORDB_ADDRESS` 주소에 해당 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="29ea0-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="29ea0-107">제한이 스택 세그먼트의 끝 `CORDB_ADDRESS` 주소인 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="29ea0-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29ea0-108">설명</span><span class="sxs-lookup"><span data-stu-id="29ea0-108">Remarks</span></span>  
 <span data-ttu-id="29ea0-109">숫자 범위는 스택 프레임 위치를 비교 하는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29ea0-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="29ea0-110">실제로 스택에 저장 되는 항목에 대 한 가정을 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29ea0-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29ea0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29ea0-111">Requirements</span></span>  
 <span data-ttu-id="29ea0-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29ea0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29ea0-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29ea0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29ea0-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29ea0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29ea0-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29ea0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
