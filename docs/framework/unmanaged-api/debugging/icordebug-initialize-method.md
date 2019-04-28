---
title: ICorDebug::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd09ce27c0fea9dca8fd86afc563651d68542e13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786362"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="996fe-102">ICorDebug::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="996fe-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="996fe-103">초기화는 `ICorDebug` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="996fe-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="996fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="996fe-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="996fe-105">설명</span><span class="sxs-lookup"><span data-stu-id="996fe-105">Remarks</span></span>  
 <span data-ttu-id="996fe-106">디버거를 호출 해야 `Initialize` 디버깅을 초기화 하는 시간을 만들 때 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="996fe-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="996fe-107">이 메서드를 다른 메서드 전에 호출 해야 `ICorDebug` 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="996fe-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="996fe-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="996fe-108">Requirements</span></span>  
 <span data-ttu-id="996fe-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="996fe-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="996fe-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="996fe-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="996fe-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="996fe-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="996fe-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="996fe-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="996fe-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="996fe-113">See also</span></span>

- [<span data-ttu-id="996fe-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="996fe-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
