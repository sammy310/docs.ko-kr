---
title: ICorDebugFrame::GetCaller 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82902e6a395fe62464065ccea4cca5b52c960f0d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492220"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="61564-102">ICorDebugFrame::GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="61564-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="61564-103">현재이 프레임 호출 체인에 ICorDebugFrame 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="61564-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61564-104">구문</span><span class="sxs-lookup"><span data-stu-id="61564-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61564-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="61564-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="61564-106">[out] 주소에 대 한 포인터를 `ICorDebugFrame` 호출 프레임을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="61564-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="61564-107">이 값은 호출된 프레임은 현재 체인의 가장 바깥쪽 프레임 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="61564-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61564-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61564-108">Requirements</span></span>  
 <span data-ttu-id="61564-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="61564-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61564-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61564-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61564-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61564-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61564-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61564-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
