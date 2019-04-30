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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f366a40e1e3cd196f480c5849c49419c7daeea9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989484"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="9c575-102">ICorDebugChain::GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="9c575-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="9c575-103">이 체인의 활성 부분에 대해 설정 하는 레지스터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c575-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c575-104">구문</span><span class="sxs-lookup"><span data-stu-id="9c575-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c575-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c575-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="9c575-106">[out] 주소에 대 한 포인터를 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 이 체인의 활성 부분에 대 한 등록을 나타내는 개체를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c575-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c575-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c575-107">Requirements</span></span>  
 <span data-ttu-id="9c575-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9c575-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c575-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c575-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c575-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c575-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c575-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c575-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
