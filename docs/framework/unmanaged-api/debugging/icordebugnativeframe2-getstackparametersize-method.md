---
description: '자세히 알아보기: ICorDebugNativeFrame2:: GetStackParameterSize 메서드'
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
ms.openlocfilehash: 08a17ced0be75737c1c49aa3f9bb42b13bbe8aa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722336"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="23f9d-103">ICorDebugNativeFrame2::GetStackParameterSize 메서드</span><span class="sxs-lookup"><span data-stu-id="23f9d-103">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>

<span data-ttu-id="23f9d-104">X86 운영 체제의 스택에 있는 매개 변수의 누적 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="23f9d-104">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23f9d-105">구문</span><span class="sxs-lookup"><span data-stu-id="23f9d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="23f9d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="23f9d-106">Parameters</span></span>  

 `pSize`  
 <span data-ttu-id="23f9d-107">제한이 스택에 있는 매개 변수의 누적 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="23f9d-107">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23f9d-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="23f9d-108">Return Value</span></span>  

 <span data-ttu-id="23f9d-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="23f9d-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="23f9d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23f9d-110">HRESULT</span></span>|<span data-ttu-id="23f9d-111">설명</span><span class="sxs-lookup"><span data-stu-id="23f9d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23f9d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="23f9d-112">S_OK</span></span>|<span data-ttu-id="23f9d-113">스택 크기가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="23f9d-113">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="23f9d-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="23f9d-114">S_FALSE</span></span>|<span data-ttu-id="23f9d-115">`GetStackParameterSize` 가 x86 이외의 플랫폼에서 호출 된 경우</span><span class="sxs-lookup"><span data-stu-id="23f9d-115">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="23f9d-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23f9d-116">E_FAIL</span></span>|<span data-ttu-id="23f9d-117">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="23f9d-117">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="23f9d-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="23f9d-118">E_INVALIDARG</span></span>|<span data-ttu-id="23f9d-119">`pSize` 는 `null` 입니다.</span><span class="sxs-lookup"><span data-stu-id="23f9d-119">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="23f9d-120">예외</span><span class="sxs-lookup"><span data-stu-id="23f9d-120">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23f9d-121">설명</span><span class="sxs-lookup"><span data-stu-id="23f9d-121">Remarks</span></span>  

 <span data-ttu-id="23f9d-122">[ICorDebugStackWalk](icordebugstackwalk-interface.md) 메서드는 스택에 푸시되는 매개 변수에 대 한 스택 포인터를 조정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23f9d-122">The [ICorDebugStackWalk](icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="23f9d-123">대신에서 반환 하는 값을 사용 하 여 `GetStackParameterSize` 스택 포인터를 조정 하 여 매개 변수에 대해 조정 하는 네이티브 해제기 초기값으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23f9d-123">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23f9d-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23f9d-124">Requirements</span></span>  

 <span data-ttu-id="23f9d-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23f9d-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23f9d-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23f9d-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23f9d-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23f9d-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23f9d-128">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23f9d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f9d-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23f9d-129">See also</span></span>

- [<span data-ttu-id="23f9d-130">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23f9d-130">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="23f9d-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23f9d-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="23f9d-132">디버깅</span><span class="sxs-lookup"><span data-stu-id="23f9d-132">Debugging</span></span>](index.md)
