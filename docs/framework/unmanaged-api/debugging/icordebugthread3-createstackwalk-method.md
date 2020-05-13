---
title: ICorDebugThread3::CreateStackWalk 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: f2850e6c9cbb2250a08ab4a0e34c69e377d3a23d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375844"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="b2cbe-102">ICorDebugThread3::CreateStackWalk 메서드</span><span class="sxs-lookup"><span data-stu-id="b2cbe-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="b2cbe-103">스택을 해제 하려는 스레드에 대 한 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2cbe-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2cbe-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2cbe-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2cbe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2cbe-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="b2cbe-106">제한이 스택을 해제 하려는 스레드에 대 한 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b2cbe-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2cbe-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="b2cbe-107">Return Value</span></span>  
 <span data-ttu-id="b2cbe-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b2cbe-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b2cbe-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2cbe-109">HRESULT</span></span>|<span data-ttu-id="b2cbe-110">설명</span><span class="sxs-lookup"><span data-stu-id="b2cbe-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2cbe-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2cbe-111">S_OK</span></span>|<span data-ttu-id="b2cbe-112">`ICorDebugStackWalk`개체를 성공적으로 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="b2cbe-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="b2cbe-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2cbe-113">E_FAIL</span></span>|<span data-ttu-id="b2cbe-114">`ICorDebugStackWalk`개체를 만들지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="b2cbe-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b2cbe-115">예외</span><span class="sxs-lookup"><span data-stu-id="b2cbe-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2cbe-116">설명</span><span class="sxs-lookup"><span data-stu-id="b2cbe-116">Remarks</span></span>  
 <span data-ttu-id="b2cbe-117">`CreateStackWalk`메서드가 성공 하면 반환 된 `ICorDebugStackWalk` 개체의 컨텍스트가 스레드의 현재 컨텍스트로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2cbe-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2cbe-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2cbe-118">Requirements</span></span>  
 <span data-ttu-id="b2cbe-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2cbe-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2cbe-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2cbe-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2cbe-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2cbe-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2cbe-122">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2cbe-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2cbe-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2cbe-123">See also</span></span>

- [<span data-ttu-id="b2cbe-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2cbe-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b2cbe-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="b2cbe-125">Debugging</span></span>](index.md)
