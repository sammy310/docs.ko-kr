---
title: ICorDebugFrame::GetCallee 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a179b68e2196eeadc712ae8f7d023b2943533335
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995854"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="a5ebc-102">ICorDebugFrame::GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="a5ebc-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="a5ebc-103">현재이 프레임에서 호출 체인에 ICorDebugFrame 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a5ebc-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ebc-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5ebc-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5ebc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5ebc-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="a5ebc-106">[out] 주소에 대 한 포인터를 `ICorDebugFrame` 호출된 프레임을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ebc-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="a5ebc-107">이 값은 호출 프레임을 현재 체인에서 가장 안쪽 프레임인 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ebc-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5ebc-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5ebc-108">Requirements</span></span>  
 <span data-ttu-id="a5ebc-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5ebc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5ebc-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5ebc-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5ebc-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5ebc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5ebc-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5ebc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
