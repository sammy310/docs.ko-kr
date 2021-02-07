---
description: '자세히 알아보기: ICorDebugRegisterSet:: GetThreadContext 메서드'
title: ICorDebugRegisterSet::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: be6384562858d04b6e139eda83c172c09f2dfc0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690803"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="62255-103">ICorDebugRegisterSet::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="62255-103">ICorDebugRegisterSet::GetThreadContext Method</span></span>

<span data-ttu-id="62255-104">현재 스레드의 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62255-104">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62255-105">구문</span><span class="sxs-lookup"><span data-stu-id="62255-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62255-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="62255-106">Parameters</span></span>  

 `contextSize`  
 <span data-ttu-id="62255-107">진행 배열의 크기 (바이트) `context` 입니다.</span><span class="sxs-lookup"><span data-stu-id="62255-107">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="62255-108">[in, out] 현재 플랫폼에 대 한 Win32 구조를 구성 하는 바이트 배열입니다 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="62255-108">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62255-109">설명</span><span class="sxs-lookup"><span data-stu-id="62255-109">Remarks</span></span>  

 <span data-ttu-id="62255-110">`GetThreadContext`스레드가 일시적으로 변경 된 "하이재킹" 상태가 될 수 있으므로 디버거가 Win32 함수 대신이 함수를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62255-110">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="62255-111">반환 된 데이터는 `CONTEXT` 현재 플랫폼에 대 한 Win32 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="62255-111">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="62255-112">리프가 아닌 프레임의 경우 클라이언트는 [ICorDebugRegisterSet:: GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md)를 사용 하 여 유효한 레지스터를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62255-112">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62255-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62255-113">Requirements</span></span>  

 <span data-ttu-id="62255-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62255-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62255-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62255-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62255-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62255-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62255-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62255-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62255-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62255-118">See also</span></span>

- [<span data-ttu-id="62255-119">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62255-119">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="62255-120">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62255-120">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
