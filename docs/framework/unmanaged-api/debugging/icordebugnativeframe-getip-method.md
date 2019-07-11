---
title: ICorDebugNativeFrame::GetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71e9149bafc866f89253c4318ac69f2705431e48
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765298"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="14c14-102">ICorDebugNativeFrame::GetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="14c14-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="14c14-103">가져옵니다 네이티브 코드 명령 포인터를 현재 설정 된 위치를 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="14c14-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14c14-104">구문</span><span class="sxs-lookup"><span data-stu-id="14c14-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14c14-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="14c14-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="14c14-106">[out] 네이티브 코드 내의 오프셋된 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="14c14-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14c14-107">설명</span><span class="sxs-lookup"><span data-stu-id="14c14-107">Remarks</span></span>  
 <span data-ttu-id="14c14-108">이 "ICorDebugNativeFrame"으로 표시 되는 스택 프레임을 활성 상태인 경우 오프셋 실행할 다음 명령의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="14c14-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="14c14-109">이 스택 프레임이 활성 상태인 경우 오프셋은 스택 프레임을 다시 활성화 될 때 실행할 다음 명령의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="14c14-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14c14-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14c14-110">Requirements</span></span>  
 <span data-ttu-id="14c14-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="14c14-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14c14-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14c14-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14c14-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14c14-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14c14-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14c14-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14c14-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="14c14-115">See also</span></span>
