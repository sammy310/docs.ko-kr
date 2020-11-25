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
ms.openlocfilehash: 5cdd89ebdbb5abb9b001c1489a54bfb867808c5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723430"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="92484-102">ICorDebug::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="92484-102">ICorDebug::Initialize Method</span></span>

<span data-ttu-id="92484-103">초기화는 `ICorDebug` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="92484-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92484-104">구문</span><span class="sxs-lookup"><span data-stu-id="92484-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="92484-105">설명</span><span class="sxs-lookup"><span data-stu-id="92484-105">Remarks</span></span>  

 <span data-ttu-id="92484-106">디버거는 `Initialize` 만들 때를 호출 하 여 디버깅 서비스를 초기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92484-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="92484-107">이 메서드는의 다른 메서드를 호출 하기 전에 호출 해야 합니다 `ICorDebug` .</span><span class="sxs-lookup"><span data-stu-id="92484-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92484-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92484-108">Requirements</span></span>  

 <span data-ttu-id="92484-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92484-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92484-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92484-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92484-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92484-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92484-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92484-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92484-113">참조</span><span class="sxs-lookup"><span data-stu-id="92484-113">See also</span></span>

- [<span data-ttu-id="92484-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92484-114">ICorDebug Interface</span></span>](icordebug-interface.md)
