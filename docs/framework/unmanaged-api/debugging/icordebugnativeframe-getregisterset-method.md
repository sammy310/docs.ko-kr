---
title: ICorDebugNativeFrame::GetRegisterSet 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6029ac8c9ab988efa78bbfaf0843154ac656671
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765792"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="dbc7e-102">ICorDebugNativeFrame::GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="dbc7e-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="dbc7e-103">이 스택 프레임에 대해 설정 하는 레지스터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dbc7e-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbc7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="dbc7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbc7e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dbc7e-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="dbc7e-106">[out] 주소에 대 한 포인터를 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 이 스택 프레임에 대 한 레지스터를 나타내는 개체를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbc7e-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbc7e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dbc7e-107">Requirements</span></span>  
 <span data-ttu-id="dbc7e-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbc7e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbc7e-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbc7e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbc7e-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbc7e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbc7e-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbc7e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc7e-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="dbc7e-112">See also</span></span>
