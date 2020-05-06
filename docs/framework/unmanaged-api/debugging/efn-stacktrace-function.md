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
ms.openlocfilehash: a725aa2c0f1fdea523bbf7cba880bc805f855782
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860740"
---
# <a name="_efn_stacktrace-function"></a><span data-ttu-id="dba02-102">\_EFN\_StackTrace 함수</span><span class="sxs-lookup"><span data-stu-id="dba02-102">\_EFN\_StackTrace Function</span></span>
<span data-ttu-id="dba02-103">비관리 코드와 관리 코드 간 각 전환에 대해 하나씩, `CONTEXT` 레코드 배열 및 관리되는 스택 추적의 텍스트 표시를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba02-104">구문</span><span class="sxs-lookup"><span data-stu-id="dba02-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="dba02-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dba02-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="dba02-106">진행 디버깅 중인 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="dba02-107">제한이 스택 추적의 텍스트 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="dba02-108">제한이 의 `wszTextOut`문자 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="dba02-109">제한이 전환 컨텍스트의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="dba02-110">제한이 배열의 전환 컨텍스트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="dba02-111">진행 컨텍스트 구조의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="dba02-112">진행 0 또는 SOS_STACKTRACE_SHOWADDRESSES (0x01)로 설정 하 여 EBP 레지스터와 각 `module!functionname` 줄 앞에 있는 ESP (enter stack 포인터)를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dba02-113">설명</span><span class="sxs-lookup"><span data-stu-id="dba02-113">Remarks</span></span>  
 <span data-ttu-id="dba02-114">이 `_EFN_StackTrace` 구조는 WinDbg 프로그래밍 인터페이스에서 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="dba02-115">매개 변수는 다음과 같이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="dba02-116">가 `wszTextOut` null이 고 `puiTextLength` 가 null이 아닌 경우 함수는의 `puiTextLength`문자열 길이를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="dba02-117">가 `wszTextOut` null이 아닌 경우 함수는에 지정 된 `wszTextOut` 위치까지 텍스트를 저장 `puiTextLength`합니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="dba02-118">버퍼에 충분 한 공간이 있으면 성공적으로 반환 되 고 버퍼가 충분 하지 않은 경우 E_OUTOFMEMORY을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="dba02-119">및 `pTransitionContexts` `puiTransitionContextCount` 가 모두 null 인 경우 함수의 전환 부분은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="dba02-120">이 경우 함수는 함수 이름에 대 한 텍스트 출력을 호출자에 게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="dba02-121">가 `pTransitionContexts` null이 고 `puiTransitionContextCount` 가 null이 아닌 경우 함수는에서 `puiTransitionContextCount`필요한 컨텍스트 항목 수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="dba02-122">가 `pTransitionContexts` null이 아닌 경우 함수는이를 길이가 `puiTransitionContextCount`인 구조체의 배열로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="dba02-123">구조 크기는에 의해 `uiSizeOfContext`제공 되며 [simplecontext](stacktrace-simplecontext-structure.md) 또는 `CONTEXT` 아키텍처용 크기 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="dba02-124">`wszTextOut`는 다음과 같은 형식으로 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="dba02-125">Hex의 오프셋이 0x0 이면 오프셋이 기록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="dba02-126">현재 컨텍스트에 있는 스레드에 관리 코드가 없으면 함수는 SOS_E_NOMANAGEDCODE 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="dba02-127">`Flags` 매개 변수는 0 또는 SOS_STACKTRACE_SHOWADDRESSES 각 `module!functionname` 줄 앞에 EBP와 ESP를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="dba02-128">기본적으로 0입니다.</span><span class="sxs-lookup"><span data-stu-id="dba02-128">By default, it is 0.</span></span>  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="dba02-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dba02-129">Requirements</span></span>  
 <span data-ttu-id="dba02-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dba02-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dba02-131">**헤더:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="dba02-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="dba02-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dba02-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba02-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dba02-133">See also</span></span>

- [<span data-ttu-id="dba02-134">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="dba02-134">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
