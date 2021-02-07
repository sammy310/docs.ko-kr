---
description: '자세히 알아보기: ICorDebugChain:: GetActiveFrame 메서드'
title: ICorDebugChain::GetActiveFrame 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
ms.openlocfilehash: d46906d9d6c671880d9446d889cdf9f83f3b4366
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661425"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="17f07-103">ICorDebugChain::GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="17f07-103">ICorDebugChain::GetActiveFrame Method</span></span>

<span data-ttu-id="17f07-104">체인의 활성 (가장 최근) 프레임을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="17f07-104">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17f07-105">구문</span><span class="sxs-lookup"><span data-stu-id="17f07-105">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17f07-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="17f07-106">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="17f07-107">제한이 체인의 활성 (가장 최근) 프레임을 나타내는 ICorDebugFrame 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="17f07-107">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17f07-108">설명</span><span class="sxs-lookup"><span data-stu-id="17f07-108">Remarks</span></span>  

 <span data-ttu-id="17f07-109">관리 되는 스택 프레임을 사용할 수 없는 경우 `ppFrame` 은 null로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17f07-109">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="17f07-110">활성 프레임을 사용할 수 없는 경우 호출은 성공 하 고 `ppFrame` null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17f07-110">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="17f07-111">CHAIN_ENTER_UNMANAGED로 인해 시작 된 체인에 대해 활성 프레임을 사용할 수 없으며, CHAIN_CLASS_INIT으로 인해 시작 된 일부 체인에 대해 활성 프레임을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17f07-111">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="17f07-112">CorDebugChainReason 열거를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="17f07-112">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17f07-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="17f07-113">Requirements</span></span>  

 <span data-ttu-id="17f07-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="17f07-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17f07-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17f07-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17f07-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17f07-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17f07-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17f07-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
