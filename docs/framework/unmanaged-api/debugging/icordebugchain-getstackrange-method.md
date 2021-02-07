---
description: '자세히 알아보기: ICorDebugChain:: GetStackRange 메서드'
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
ms.openlocfilehash: 066dda06564655350d799dabb54acd622b828172
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694932"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="2e4cc-103">ICorDebugChain::GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="2e4cc-103">ICorDebugChain::GetStackRange Method</span></span>

<span data-ttu-id="2e4cc-104">이 체인의 스택 세그먼트에 대 한 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2e4cc-104">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e4cc-105">구문</span><span class="sxs-lookup"><span data-stu-id="2e4cc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e4cc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e4cc-106">Parameters</span></span>  

 `pStart`  
 <span data-ttu-id="2e4cc-107">제한이 스택 세그먼트의 시작 주소에 해당 하는 값에 대 한 포인터입니다 `CORDB_ADDRESS` .</span><span class="sxs-lookup"><span data-stu-id="2e4cc-107">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="2e4cc-108">제한이 `CORDB_ADDRESS` 스택 세그먼트의 끝 주소인 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2e4cc-108">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e4cc-109">설명</span><span class="sxs-lookup"><span data-stu-id="2e4cc-109">Remarks</span></span>  

 <span data-ttu-id="2e4cc-110">숫자 범위는 스택 프레임 위치를 비교 하는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e4cc-110">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="2e4cc-111">실제로 스택에 저장 되는 항목에 대 한 가정을 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e4cc-111">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e4cc-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e4cc-112">Requirements</span></span>  

 <span data-ttu-id="2e4cc-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e4cc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e4cc-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e4cc-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e4cc-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e4cc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e4cc-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e4cc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
