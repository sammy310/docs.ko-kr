---
title: ICorDebugFrame::CreateStepper 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
ms.openlocfilehash: 39b4e7e5123447a36254b55b6168c80e48c8dcab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205443"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="3a259-102">ICorDebugFrame::CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="3a259-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="3a259-103">디버거가이 ICorDebugFrame에 비해 단계별 작업을 수행할 수 있도록 하는 스텝 퍼를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a259-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a259-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a259-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a259-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a259-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="3a259-106">제한이 디버거가 현재 프레임에 상대적인 단계별 작업을 수행할 수 있도록 하는 ICorDebugStepper 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a259-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a259-107">설명</span><span class="sxs-lookup"><span data-stu-id="3a259-107">Remarks</span></span>  
 <span data-ttu-id="3a259-108">프레임이 활성화 되어 있지 않으면 단계가 완료 되기 전에 스텝 퍼 개체가 프레임으로 돌아가야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a259-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a259-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a259-109">Requirements</span></span>  
 <span data-ttu-id="3a259-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a259-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a259-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a259-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a259-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a259-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a259-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a259-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
