---
title: ICorDebugILFrame::CanSetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75b28dafae2861a2d33363f95a46bf1abf4cda35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756583"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="d7312-102">ICorDebugILFrame::CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="d7312-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="d7312-103">명령 포인터 중간 MSIL (Microsoft Language) 코드에서 지정된 된 오프셋된 위치를 설정할 수 있는지 여부를 나타내는 HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7312-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7312-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7312-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7312-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7312-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="d7312-106">[in] 명령 포인터에 대 한 원하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="d7312-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7312-107">설명</span><span class="sxs-lookup"><span data-stu-id="d7312-107">Remarks</span></span>  
 <span data-ttu-id="d7312-108">사용 된 `CanSetIP` 메서드를 호출 하기 전에 [icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d7312-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="d7312-109">하는 경우 `CanSetIP` HRESULT를 반환 S_OK 이외의 여전히를 호출할 수 있습니다 `ICorDebugILFrame::SetIP`, 이지만 디버거에서 디버깅 중인 코드가 안전 하 고 올바른 실행을 계속는 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7312-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7312-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7312-110">Requirements</span></span>  
 <span data-ttu-id="d7312-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7312-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7312-112">**헤더:** CorDebug.idl, CorDebug,h</span><span class="sxs-lookup"><span data-stu-id="d7312-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="d7312-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7312-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7312-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7312-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
