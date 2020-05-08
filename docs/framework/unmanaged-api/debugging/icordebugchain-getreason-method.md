---
title: ICorDebugChain::GetReason 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type:
- apiref
ms.openlocfilehash: 94672c88864efc431acde8f29e406f4fbbc644ee
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894552"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="9c6da-102">ICorDebugChain::GetReason 메서드</span><span class="sxs-lookup"><span data-stu-id="9c6da-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="9c6da-103">이 호출 체인의 genesis 이유를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c6da-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c6da-104">구문</span><span class="sxs-lookup"><span data-stu-id="9c6da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c6da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c6da-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="9c6da-106">제한이 이 호출 체인의 genesis에 대 한 이유를 나타내는 CorDebugChainReason 열거형의 값 (비트 조합)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c6da-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c6da-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c6da-107">Requirements</span></span>  
 <span data-ttu-id="9c6da-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c6da-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c6da-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c6da-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c6da-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c6da-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c6da-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c6da-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
