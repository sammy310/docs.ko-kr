---
description: '자세히 알아보기: ICorDebugProcess:: ThreadForFiberCookie 메서드'
title: ICorDebugProcess::ThreadForFiberCookie 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ThreadForFiberCookie
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ThreadForFiberCookie
helpviewer_keywords:
- ICorDebugProcess::ThreadForFiberCookie method [.NET Framework debugging]
- ThreadForFiberCookie method [.NET Framework debugging]
ms.assetid: afe4e97f-bffc-47e1-adad-d6e842487f35
topic_type:
- apiref
ms.openlocfilehash: e3618d08f0b5212dbc8502194926c9ae0c97744b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650201"
---
# <a name="icordebugprocessthreadforfibercookie-method"></a><span data-ttu-id="36718-103">ICorDebugProcess::ThreadForFiberCookie 메서드</span><span class="sxs-lookup"><span data-stu-id="36718-103">ICorDebugProcess::ThreadForFiberCookie Method</span></span>

<span data-ttu-id="36718-104">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="36718-104">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36718-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="36718-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadForFiberCookie (  
    [in] DWORD fiberCookie,  
    [out] ICorDebugThread **ppThread  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="36718-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36718-106">Requirements</span></span>  

 <span data-ttu-id="36718-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36718-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36718-108">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36718-108">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36718-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36718-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36718-110">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36718-110">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
