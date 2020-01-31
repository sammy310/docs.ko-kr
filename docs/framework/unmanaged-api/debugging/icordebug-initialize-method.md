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
ms.openlocfilehash: 3d27cf1987d7e9896885f87857554f4039c8d714
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788986"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="4f3a4-102">ICorDebug::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="4f3a4-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="4f3a4-103">초기화는 `ICorDebug` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4f3a4-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f3a4-104">구문</span><span class="sxs-lookup"><span data-stu-id="4f3a4-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4f3a4-105">주의</span><span class="sxs-lookup"><span data-stu-id="4f3a4-105">Remarks</span></span>  
 <span data-ttu-id="4f3a4-106">디버거는 만든 시간에 `Initialize`를 호출 하 여 디버깅 서비스를 초기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3a4-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="4f3a4-107">`ICorDebug`에서 다른 메서드를 호출 하기 전에이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3a4-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f3a4-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f3a4-108">Requirements</span></span>  
 <span data-ttu-id="4f3a4-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f3a4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f3a4-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f3a4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f3a4-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f3a4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f3a4-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f3a4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f3a4-113">참조</span><span class="sxs-lookup"><span data-stu-id="4f3a4-113">See also</span></span>

- [<span data-ttu-id="4f3a4-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f3a4-114">ICorDebug Interface</span></span>](icordebug-interface.md)
