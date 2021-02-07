---
description: '자세히 알아보기: ICorDebugChain:: GetReason 메서드'
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
ms.openlocfilehash: 0952d09db6d43f7970ba9e8c46c409fb2cd4b131
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694971"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="5a214-103">ICorDebugChain::GetReason 메서드</span><span class="sxs-lookup"><span data-stu-id="5a214-103">ICorDebugChain::GetReason Method</span></span>

<span data-ttu-id="5a214-104">이 호출 체인의 genesis 이유를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-104">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a214-105">구문</span><span class="sxs-lookup"><span data-stu-id="5a214-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a214-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a214-106">Parameters</span></span>  

 `pReason`  
 <span data-ttu-id="5a214-107">제한이 이 호출 체인의 genesis에 대 한 이유를 나타내는 CorDebugChainReason 열거형의 값 (비트 조합)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5a214-107">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a214-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a214-108">Requirements</span></span>  

 <span data-ttu-id="5a214-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a214-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a214-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a214-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a214-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a214-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a214-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a214-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
