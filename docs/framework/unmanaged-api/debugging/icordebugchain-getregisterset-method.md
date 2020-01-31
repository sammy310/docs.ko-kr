---
title: ICorDebugChain::GetRegisterSet 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetRegisterSet
helpviewer_keywords:
- ICorDebugChain::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: bc4288b6-3331-4ae3-990d-e1d6e62ecb67
topic_type:
- apiref
ms.openlocfilehash: 1a435226fca775d7dd38a4c5dd35eac3078b092b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784294"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="f9391-102">ICorDebugChain::GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="f9391-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="f9391-103">이 체인의 활성 부분에 대 한 레지스터 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f9391-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9391-104">구문</span><span class="sxs-lookup"><span data-stu-id="f9391-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9391-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f9391-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="f9391-106">제한이 이 체인의 활성 부분에 대 한 레지스터 집합을 나타내는 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f9391-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9391-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9391-107">Requirements</span></span>  
 <span data-ttu-id="f9391-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9391-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9391-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9391-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9391-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9391-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9391-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9391-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
