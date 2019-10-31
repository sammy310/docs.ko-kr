---
title: ICorDebugNativeFrame::CanSetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: b3758ac1a84092b8bf2678f9cc2c19c9d9961690
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137321"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="f921f-102">ICorDebugNativeFrame::CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="f921f-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="f921f-103">네이티브 코드에서 지정 된 오프셋 위치로 IP (명령 포인터)를 설정 하는 것이 안전한 지 여부를 나타내는 HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f921f-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f921f-104">구문</span><span class="sxs-lookup"><span data-stu-id="f921f-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f921f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f921f-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="f921f-106">진행 명령 포인터에 대 한 원하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="f921f-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f921f-107">주의</span><span class="sxs-lookup"><span data-stu-id="f921f-107">Remarks</span></span>  
 <span data-ttu-id="f921f-108">[ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) 메서드를 호출 하기 전에 `CanSetIP` 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f921f-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="f921f-109">`CanSetIP` S_OK 이외의 HRESULT를 반환 하는 경우에도 `ICorDebugNativeFrame::SetIP`를 호출할 수 있지만 디버거는 디버깅 중인 코드의 안전 하 고 올바른 실행을 계속 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f921f-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f921f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f921f-110">Requirements</span></span>  
 <span data-ttu-id="f921f-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f921f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f921f-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f921f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f921f-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f921f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f921f-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f921f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f921f-115">참조</span><span class="sxs-lookup"><span data-stu-id="f921f-115">See also</span></span>
