---
title: ICorDebugNativeFrame2::GetStackParameterSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
ms.openlocfilehash: 21af3980de9b5a768b6af9a8aca74b693c7ac528
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695493"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="cd2cf-102">ICorDebugNativeFrame2::GetStackParameterSize 메서드</span><span class="sxs-lookup"><span data-stu-id="cd2cf-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>

<span data-ttu-id="cd2cf-103">X86 운영 체제의 스택에 있는 매개 변수의 누적 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd2cf-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd2cf-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd2cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd2cf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd2cf-105">Parameters</span></span>  

 `pSize`  
 <span data-ttu-id="cd2cf-106">제한이 스택에 있는 매개 변수의 누적 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd2cf-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd2cf-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="cd2cf-107">Return Value</span></span>  

 <span data-ttu-id="cd2cf-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cd2cf-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="cd2cf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd2cf-109">HRESULT</span></span>|<span data-ttu-id="cd2cf-110">설명</span><span class="sxs-lookup"><span data-stu-id="cd2cf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd2cf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd2cf-111">S_OK</span></span>|<span data-ttu-id="cd2cf-112">스택 크기가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd2cf-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="cd2cf-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="cd2cf-113">S_FALSE</span></span>|<span data-ttu-id="cd2cf-114">`GetStackParameterSize` 가 x86 이외의 플랫폼에서 호출 된 경우</span><span class="sxs-lookup"><span data-stu-id="cd2cf-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="cd2cf-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd2cf-115">E_FAIL</span></span>|<span data-ttu-id="cd2cf-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="cd2cf-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="cd2cf-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cd2cf-117">E_INVALIDARG</span></span>|<span data-ttu-id="cd2cf-118">`pSize` 는 `null` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cd2cf-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="cd2cf-119">예외</span><span class="sxs-lookup"><span data-stu-id="cd2cf-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd2cf-120">설명</span><span class="sxs-lookup"><span data-stu-id="cd2cf-120">Remarks</span></span>  

 <span data-ttu-id="cd2cf-121">[ICorDebugStackWalk](icordebugstackwalk-interface.md) 메서드는 스택에 푸시되는 매개 변수에 대 한 스택 포인터를 조정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd2cf-121">The [ICorDebugStackWalk](icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="cd2cf-122">대신에서 반환 하는 값을 사용 하 여 `GetStackParameterSize` 스택 포인터를 조정 하 여 매개 변수에 대해 조정 하는 네이티브 해제기 초기값으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd2cf-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd2cf-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd2cf-123">Requirements</span></span>  

 <span data-ttu-id="cd2cf-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd2cf-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd2cf-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd2cf-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd2cf-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd2cf-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd2cf-127">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd2cf-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd2cf-128">참조</span><span class="sxs-lookup"><span data-stu-id="cd2cf-128">See also</span></span>

- [<span data-ttu-id="cd2cf-129">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd2cf-129">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="cd2cf-130">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd2cf-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="cd2cf-131">디버깅</span><span class="sxs-lookup"><span data-stu-id="cd2cf-131">Debugging</span></span>](index.md)
