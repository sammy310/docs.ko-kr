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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 051491173bbcef3d87d9a3dbe854eece46c49e0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994060"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="98004-102">ICorDebugThread::GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="98004-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="98004-103">이 ICorDebugThread 개체의 활성 (가장 최근) 프레임에는 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98004-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98004-104">구문</span><span class="sxs-lookup"><span data-stu-id="98004-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98004-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98004-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="98004-106">[out] 프레임을 나타내는 ICorDebugFrame 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="98004-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98004-107">설명</span><span class="sxs-lookup"><span data-stu-id="98004-107">Remarks</span></span>  
 <span data-ttu-id="98004-108">`ppFrame` 매개 변수가 없는 프레임이 현재 활성화 되어 있으면 null입니다.</span><span class="sxs-lookup"><span data-stu-id="98004-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98004-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98004-109">Requirements</span></span>  
 <span data-ttu-id="98004-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98004-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98004-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98004-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98004-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98004-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98004-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98004-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
