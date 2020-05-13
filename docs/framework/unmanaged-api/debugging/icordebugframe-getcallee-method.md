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
ms.openlocfilehash: 51ac10f936db129282720f2bcae8729f56735b59
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205375"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="6ef7e-102">ICorDebugFrame::GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="6ef7e-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="6ef7e-103">이 프레임이 호출 하는 현재 체인의 ICorDebugFrame 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ef7e-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ef7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ef7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ef7e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ef7e-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="6ef7e-106">제한이 호출 된 프레임을 나타내는 개체의 주소에 대 한 포인터 `ICorDebugFrame` 입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef7e-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="6ef7e-107">호출 하는 프레임이 현재 체인에서 가장 안쪽 프레임 이면이 값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef7e-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ef7e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ef7e-108">Requirements</span></span>  
 <span data-ttu-id="6ef7e-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ef7e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ef7e-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ef7e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ef7e-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ef7e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ef7e-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ef7e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
