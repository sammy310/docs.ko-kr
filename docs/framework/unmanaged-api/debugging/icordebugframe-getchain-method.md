---
title: ICorDebugFrame::GetChain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64de770676cdd02375e854acb8af7feecb28dfeb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754116"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="79474-102">ICorDebugFrame::GetChain 메서드</span><span class="sxs-lookup"><span data-stu-id="79474-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="79474-103">이 프레임의 일부인 체인에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="79474-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79474-104">구문</span><span class="sxs-lookup"><span data-stu-id="79474-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79474-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="79474-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="79474-106">[out] 이 프레임에 포함 된 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="79474-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79474-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="79474-107">Requirements</span></span>  
 <span data-ttu-id="79474-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="79474-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79474-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79474-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79474-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79474-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79474-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79474-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
