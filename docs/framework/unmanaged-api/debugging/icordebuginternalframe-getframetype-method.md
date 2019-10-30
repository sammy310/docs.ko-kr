---
title: ICorDebugInternalFrame::GetFrameType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
ms.openlocfilehash: b7a33fd6e2178e0e9188b81f516b231702fb6460
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122722"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="0d307-102">ICorDebugInternalFrame::GetFrameType 메서드</span><span class="sxs-lookup"><span data-stu-id="0d307-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="0d307-103">이 내부 프레임의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d307-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d307-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d307-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d307-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d307-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="0d307-106">제한이 이 `ICorDebugInternalFrame` 개체가 나타내는 내부 프레임의 형식을 나타내는 CorDebugInternalFrameType 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0d307-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d307-107">주의</span><span class="sxs-lookup"><span data-stu-id="0d307-107">Remarks</span></span>  
 <span data-ttu-id="0d307-108">내부 프레임 형식은 STUBFRAME_NONE 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d307-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="0d307-109">디버거는 인식 되지 않는 내부 프레임 형식을 정상적으로 무시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d307-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d307-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d307-110">Requirements</span></span>  
 <span data-ttu-id="0d307-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d307-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d307-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d307-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d307-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d307-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d307-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d307-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
