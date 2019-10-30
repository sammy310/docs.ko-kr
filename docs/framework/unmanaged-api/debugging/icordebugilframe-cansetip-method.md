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
ms.openlocfilehash: 57d83d1f301cbfd43f8f553d9aef4beb3baf95f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131080"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="e3c7e-102">ICorDebugILFrame::CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="e3c7e-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="e3c7e-103">MSIL (Microsoft 중간 언어) 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 하는 것이 안전한 지 여부를 나타내는 HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3c7e-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3c7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3c7e-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3c7e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3c7e-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="e3c7e-106">진행 명령 포인터에 대 한 원하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="e3c7e-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3c7e-107">주의</span><span class="sxs-lookup"><span data-stu-id="e3c7e-107">Remarks</span></span>  
 <span data-ttu-id="e3c7e-108">[ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) 메서드를 호출 하기 전에 `CanSetIP` 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c7e-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="e3c7e-109">`CanSetIP` S_OK 이외의 HRESULT를 반환 하는 경우에도 `ICorDebugILFrame::SetIP`를 호출할 수 있지만 디버거는 디버깅 중인 코드의 안전 하 고 올바른 실행을 계속 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c7e-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3c7e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3c7e-110">Requirements</span></span>  
 <span data-ttu-id="e3c7e-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3c7e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3c7e-112">**헤더:** CorDebug .idl, CorDebug, h</span><span class="sxs-lookup"><span data-stu-id="e3c7e-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="e3c7e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3c7e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3c7e-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3c7e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
