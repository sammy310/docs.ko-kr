---
title: _EFN_StackTrace 함수
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 687fdd0735e6cb0f3a727c8a2da3cf33bffb6a39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738975"
---
# <a name="efnstacktrace-function"></a><span data-ttu-id="5f76f-102">\_EFN\_StackTrace 함수</span><span class="sxs-lookup"><span data-stu-id="5f76f-102">\_EFN\_StackTrace Function</span></span>
<span data-ttu-id="5f76f-103">비관리 코드와 관리 코드 간 각 전환에 대해 하나씩, `CONTEXT` 레코드 배열 및 관리되는 스택 추적의 텍스트 표시를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f76f-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f76f-104">Syntax</span></span>  
  
```cpp  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f76f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f76f-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="5f76f-106">[in] 디버깅 중인 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="5f76f-107">[out] 스택 추적의 텍스트 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="5f76f-108">[out] 에 있는 문자의 수에 대 한 포인터 `wszTextOut`합니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="5f76f-109">[out] 컨텍스트 전환의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="5f76f-110">[out] 배열에서 컨텍스트 전환 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="5f76f-111">[in] 상황에 맞는 구조체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="5f76f-112">[in] 0 또는 SOS_STACKTRACE_SHOWADDRESSES (0x01) EBP 레지스터 및 각 앞에 입력 스택 포인터 ESP ()를 표시 하도록로 `module!functionname` 줄.</span><span class="sxs-lookup"><span data-stu-id="5f76f-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f76f-113">설명</span><span class="sxs-lookup"><span data-stu-id="5f76f-113">Remarks</span></span>  
 <span data-ttu-id="5f76f-114">`_EFN_StackTrace` WinDbg 프로그래밍 인터페이스에서 구조를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="5f76f-115">매개 변수는 다음과 같이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="5f76f-116">하는 경우 `wszTextOut` isnull 및 `puiTextLength` 는 null이 아닌 함수에서 문자열 길이 반환 `puiTextLength`합니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="5f76f-117">하는 경우 `wszTextOut` 가 null이 아닌 함수에 텍스트를 저장 `wszTextOut` 가리키는 위치까지 `puiTextLength`입니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="5f76f-118">버퍼 길이가 짧습니다 경우 충분 한 공간이 버퍼 또는 e_outofmemory가 반환 되었으면 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="5f76f-119">전환에 대 한 부분 함수는 무시 됩니다 `pTransitionContexts` 고 `puiTransitionContextCount` 둘 다 null입니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="5f76f-120">이 경우 함수는 함수 이름만의 텍스트 출력을 사용 하 여 호출자에 게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="5f76f-121">경우 `pTransitionContexts` isnull 및 `puiTransitionContextCount` 는 null이 아닌 반환에서 상황에 맞는 항목 수가 필요한 `puiTransitionContextCount`합니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="5f76f-122">하는 경우 `pTransitionContexts` 가 null이 아닌 함수 처리 길이의 구조의 배열로 `puiTransitionContextCount`합니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="5f76f-123">구조체의 크기가 지정 하 여 `uiSizeOfContext`, 크기 여야 [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) 또는 `CONTEXT` 아키텍처에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="5f76f-124">`wszTextOut` 다음 형식으로 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="5f76f-125">16 진수 오프셋 0x0 인 경우 오프셋 없이 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="5f76f-126">경우에 관리 코드가 없는 스레드에서 현재 컨텍스트에서 SOS_E_NOMANAGEDCODE 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="5f76f-127">합니다 `Flags` 매개 변수는 0 또는 각 앞에 EBP 및 ESP를 보려는 SOS_STACKTRACE_SHOWADDRESSES `module!functionname` 줄.</span><span class="sxs-lookup"><span data-stu-id="5f76f-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="5f76f-128">기본적으로 0입니다.</span><span class="sxs-lookup"><span data-stu-id="5f76f-128">By default, it is 0.</span></span>  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="5f76f-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f76f-129">Requirements</span></span>  
 <span data-ttu-id="5f76f-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f76f-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f76f-131">**헤더:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="5f76f-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="5f76f-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f76f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f76f-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="5f76f-133">See also</span></span>

- [<span data-ttu-id="5f76f-134">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5f76f-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
