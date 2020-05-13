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
ms.openlocfilehash: 6b598352f734cf47514a82de1d0fca65d430a9ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209970"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="0fee4-102">ICorDebugInternalFrame::GetFrameType 메서드</span><span class="sxs-lookup"><span data-stu-id="0fee4-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="0fee4-103">이 내부 프레임의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0fee4-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fee4-104">구문</span><span class="sxs-lookup"><span data-stu-id="0fee4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fee4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0fee4-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="0fee4-106">제한이 이 개체가 나타내는 내부 프레임의 형식을 나타내는 CorDebugInternalFrameType 열거형의 값에 대 한 포인터입니다 `ICorDebugInternalFrame` .</span><span class="sxs-lookup"><span data-stu-id="0fee4-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fee4-107">설명</span><span class="sxs-lookup"><span data-stu-id="0fee4-107">Remarks</span></span>  
 <span data-ttu-id="0fee4-108">내부 프레임 형식은 STUBFRAME_NONE 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fee4-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="0fee4-109">디버거는 인식 되지 않는 내부 프레임 형식을 정상적으로 무시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fee4-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fee4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0fee4-110">Requirements</span></span>  
 <span data-ttu-id="0fee4-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fee4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fee4-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fee4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fee4-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fee4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fee4-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fee4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
