---
description: '자세히 알아보기: ICorDebug:: Initialize 메서드'
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
ms.openlocfilehash: 6b6ddd8c1c21470477420909bcf75906b5731ee6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791597"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="508d5-103">ICorDebug::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="508d5-103">ICorDebug::Initialize Method</span></span>

<span data-ttu-id="508d5-104">초기화는 `ICorDebug` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="508d5-104">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="508d5-105">구문</span><span class="sxs-lookup"><span data-stu-id="508d5-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="508d5-106">설명</span><span class="sxs-lookup"><span data-stu-id="508d5-106">Remarks</span></span>  

 <span data-ttu-id="508d5-107">디버거는 `Initialize` 만들 때를 호출 하 여 디버깅 서비스를 초기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="508d5-107">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="508d5-108">이 메서드는의 다른 메서드를 호출 하기 전에 호출 해야 합니다 `ICorDebug` .</span><span class="sxs-lookup"><span data-stu-id="508d5-108">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="508d5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="508d5-109">Requirements</span></span>  

 <span data-ttu-id="508d5-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="508d5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="508d5-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="508d5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="508d5-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="508d5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="508d5-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="508d5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="508d5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="508d5-114">See also</span></span>

- [<span data-ttu-id="508d5-115">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="508d5-115">ICorDebug Interface</span></span>](icordebug-interface.md)
