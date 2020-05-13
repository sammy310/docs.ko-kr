---
title: ICorDebugILFrame::SetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
ms.openlocfilehash: 325b2a009e77d87e95bdb02803dd3c4675c26ddc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213428"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="18664-102">ICorDebugILFrame::SetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="18664-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="18664-103">MSIL (Microsoft 중간 언어) 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="18664-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18664-104">구문</span><span class="sxs-lookup"><span data-stu-id="18664-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18664-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18664-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="18664-106">MSIL 코드의 오프셋 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="18664-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18664-107">설명</span><span class="sxs-lookup"><span data-stu-id="18664-107">Remarks</span></span>  
 <span data-ttu-id="18664-108">를 호출 `SetIP` 하면 현재 스레드에 대 한 모든 프레임과 체인이 즉시 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18664-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="18664-109">를 호출한 후 디버거에 프레임 정보가 필요한 경우 `SetIP` 새 스택 추적을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18664-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="18664-110">[ICorDebug](icordebug-interface.md) 는 스택 프레임을 유효한 상태로 유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="18664-110">[ICorDebug](icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="18664-111">그러나 프레임이 유효한 상태 이더라도 초기화 되지 않은 지역 변수 같은 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18664-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="18664-112">호출자는 실행 중인 프로그램의 일관성을 보장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18664-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="18664-113">64 비트 플랫폼에서 명령 포인터는 또는 블록 밖으로 이동할 수 없습니다 `catch` `finally` .</span><span class="sxs-lookup"><span data-stu-id="18664-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="18664-114">을 `SetIP` 호출 하 여 64 비트 플랫폼에서 이러한 이동을 수행 하는 경우 실패를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="18664-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18664-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18664-115">Requirements</span></span>  
 <span data-ttu-id="18664-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18664-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18664-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18664-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18664-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18664-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18664-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18664-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
