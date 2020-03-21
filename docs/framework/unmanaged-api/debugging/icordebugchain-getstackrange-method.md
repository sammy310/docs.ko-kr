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
ms.openlocfilehash: 64e697323377d664b7b1e36bbf5931a44465cc51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178952"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="19774-102">ICorDebugChain::GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="19774-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="19774-103">이 체인의 스택 세그먼트의 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19774-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19774-104">구문</span><span class="sxs-lookup"><span data-stu-id="19774-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19774-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19774-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="19774-106">【아웃】 스택 세그먼트의 `CORDB_ADDRESS` 시작 주소인 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="19774-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="19774-107">【아웃】 스택 세그먼트의 `CORDB_ADDRESS` 끝 주소인 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="19774-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19774-108">설명</span><span class="sxs-lookup"><span data-stu-id="19774-108">Remarks</span></span>  
 <span data-ttu-id="19774-109">숫자 범위는 스택 프레임 위치를 비교하는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19774-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="19774-110">스택에 실제로 저장 되는 것에 대 한 어떤 가정을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19774-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19774-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19774-111">Requirements</span></span>  
 <span data-ttu-id="19774-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19774-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19774-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19774-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19774-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19774-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19774-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19774-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
