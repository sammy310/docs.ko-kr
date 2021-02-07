---
description: '자세히 알아보기: ICorDebugEval:: CallFunction 메서드'
title: ICorDebugEval::CallFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
ms.openlocfilehash: c0978ab3bdffc83e3eb5e3a6553e7f374ab6d5da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694190"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="a8ff6-103">ICorDebugEval::CallFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="a8ff6-103">ICorDebugEval::CallFunction Method</span></span>

<span data-ttu-id="a8ff6-104">지정 된 함수에 대 한 호출을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ff6-104">Sets up a call to the specified function.</span></span>

<span data-ttu-id="a8ff6-105">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ff6-105">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a8ff6-106">대신 [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ff6-106">Use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8ff6-107">구문</span><span class="sxs-lookup"><span data-stu-id="a8ff6-107">Syntax</span></span>

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a><span data-ttu-id="a8ff6-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8ff6-108">Parameters</span></span>

`pFunction`\
<span data-ttu-id="a8ff6-109">진행 호출할 함수를 지정 하는 ICorDebugFunction 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8ff6-109">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>

`nArgs`\
<span data-ttu-id="a8ff6-110">진행 함수에 대 한 인수 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="a8ff6-110">[in] The number of arguments for the function.</span></span>

`ppArgs`\
<span data-ttu-id="a8ff6-111">진행 각각 함수에 전달 될 인수를 지정 하는 ICorDebugValue 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a8ff6-111">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8ff6-112">설명</span><span class="sxs-lookup"><span data-stu-id="a8ff6-112">Remarks</span></span>

<span data-ttu-id="a8ff6-113">함수가 virtual 인 경우는 `CallFunction` 가상 디스패치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ff6-113">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="a8ff6-114">함수가 다른 응용 프로그램 도메인에 있는 경우 모든 인수가 해당 응용 프로그램 도메인에 있는 경우에만 전환이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8ff6-114">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>

## <a name="requirements"></a><span data-ttu-id="a8ff6-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8ff6-115">Requirements</span></span>

<span data-ttu-id="a8ff6-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8ff6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a8ff6-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8ff6-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="a8ff6-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8ff6-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a8ff6-119">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="a8ff6-119">**.NET Framework Versions:** 1.1, 1.0</span></span>

## <a name="see-also"></a><span data-ttu-id="a8ff6-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8ff6-120">See also</span></span>

- [<span data-ttu-id="a8ff6-121">CallParameterizedFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="a8ff6-121">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)
