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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0b6f0550bad534379b562c3df9da9ab917f5270
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493039"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="500a3-102">ICorDebugInternalFrame::GetFrameType 메서드</span><span class="sxs-lookup"><span data-stu-id="500a3-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="500a3-103">이 내부 프레임의 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="500a3-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="500a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="500a3-104">Syntax</span></span>  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="500a3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="500a3-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="500a3-106">[out] 이 나타내는 내부 프레임의 유형을 나타내는 CorDebugInternalFrameType 열거형의 값에 대 한 포인터 `ICorDebugInternalFrame` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="500a3-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="500a3-107">설명</span><span class="sxs-lookup"><span data-stu-id="500a3-107">Remarks</span></span>  
 <span data-ttu-id="500a3-108">내부 프레임 유형 STUBFRAME_NONE 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="500a3-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="500a3-109">디버거는 인식할 수 없는 내부 프레임 형식을 무시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="500a3-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="500a3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="500a3-110">Requirements</span></span>  
 <span data-ttu-id="500a3-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="500a3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="500a3-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="500a3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="500a3-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="500a3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="500a3-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="500a3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
