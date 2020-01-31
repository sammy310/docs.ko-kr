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
ms.openlocfilehash: d266ec7f82d7d4c7c66f137aafc1c8865d6f8889
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792798"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="02af7-102">ICorDebugNativeFrame::CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="02af7-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="02af7-103">네이티브 코드에서 지정 된 오프셋 위치로 IP (명령 포인터)를 설정 하는 것이 안전한 지 여부를 나타내는 HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02af7-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02af7-104">구문</span><span class="sxs-lookup"><span data-stu-id="02af7-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02af7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02af7-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="02af7-106">진행 명령 포인터에 대 한 원하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="02af7-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02af7-107">주의</span><span class="sxs-lookup"><span data-stu-id="02af7-107">Remarks</span></span>  
 <span data-ttu-id="02af7-108">[ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) 메서드를 호출 하기 전에 `CanSetIP` 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="02af7-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="02af7-109">`CanSetIP`에서 S_OK 이외의 HRESULT를 반환 하는 경우에도 여전히 `ICorDebugNativeFrame::SetIP`를 호출할 수 있지만 디버거는 디버깅 중인 코드의 안전 하 고 올바른 실행을 계속 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02af7-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02af7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02af7-110">Requirements</span></span>  
 <span data-ttu-id="02af7-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02af7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02af7-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02af7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02af7-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02af7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02af7-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02af7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02af7-115">참조</span><span class="sxs-lookup"><span data-stu-id="02af7-115">See also</span></span>
