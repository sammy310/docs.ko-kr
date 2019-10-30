---
title: ICorDebugThread::GetActiveFrame 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
ms.openlocfilehash: d623893bd77e46832b0bd823ed60c23e4eee29ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133533"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="4009c-102">ICorDebugThread::GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="4009c-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="4009c-103">이 ICorDebugThread 개체의 활성 (가장 최근) 프레임에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4009c-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4009c-104">구문</span><span class="sxs-lookup"><span data-stu-id="4009c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4009c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4009c-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="4009c-106">제한이 프레임을 나타내는 ICorDebugFrame interface 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4009c-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4009c-107">주의</span><span class="sxs-lookup"><span data-stu-id="4009c-107">Remarks</span></span>  
 <span data-ttu-id="4009c-108">현재 활성화 된 프레임이 없는 경우 `ppFrame` 매개 변수는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="4009c-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4009c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4009c-109">Requirements</span></span>  
 <span data-ttu-id="4009c-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4009c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4009c-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4009c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4009c-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4009c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4009c-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4009c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
