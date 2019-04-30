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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac40927ac9469e4a2fb74fb550287130b9bb9f83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989458"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="087da-102">ICorDebugChain::GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="087da-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="087da-103">이 체인에 대 한 스택 세그먼트의 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="087da-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="087da-104">구문</span><span class="sxs-lookup"><span data-stu-id="087da-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="087da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="087da-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="087da-106">[out] 에 대 한 포인터를 `CORDB_ADDRESS` 스택 세그먼트의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="087da-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="087da-107">[out] 에 대 한 포인터를 `CORDB_ADDRESS` 값 스택 세그먼트의 끝 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="087da-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="087da-108">설명</span><span class="sxs-lookup"><span data-stu-id="087da-108">Remarks</span></span>  
 <span data-ttu-id="087da-109">숫자 범위는 스택 프레임 위치를 비교 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="087da-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="087da-110">실제로 스택에 저장 된 대 한 가정을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="087da-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="087da-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="087da-111">Requirements</span></span>  
 <span data-ttu-id="087da-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="087da-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="087da-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="087da-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="087da-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="087da-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="087da-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="087da-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
