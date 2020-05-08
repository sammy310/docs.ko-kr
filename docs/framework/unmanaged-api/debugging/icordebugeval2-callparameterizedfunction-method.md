---
title: ICorDebugEval2::CallParameterizedFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
ms.openlocfilehash: 72bcc2479f7b6f41b384fc2517f0b04694663398
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976150"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="e8803-102">ICorDebugEval2::CallParameterizedFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="e8803-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="e8803-103">생성자가 매개 변수를 사용 <xref:System.Type> 하거나 <xref:System.Type> 매개 변수를 사용할 수 있는 클래스 내에 중첩 될 수 있는 지정 된 ICorDebugFunction에 대 한 호출을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8803-104">구문</span><span class="sxs-lookup"><span data-stu-id="e8803-104">Syntax</span></span>  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8803-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e8803-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="e8803-106">진행 호출할 함수를 나타내는 `ICorDebugFunction` 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="e8803-107">진행 함수가 사용 하는 인수 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="e8803-108">진행 각각 함수 인수를 나타내는 ICorDebugType 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="e8803-109">진행 함수에 전달 된 값의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="e8803-110">진행 각각 함수 인수에 전달 된 값을 나타내는 ICorDebugValue 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8803-111">설명</span><span class="sxs-lookup"><span data-stu-id="e8803-111">Remarks</span></span>  
 <span data-ttu-id="e8803-112">`CallParameterizedFunction`함수는 형식 매개 변수가 있는 클래스 내부에 있을 수 있다는 점을 제외 하 고는 [ICorDebugEval:: CallFunction](icordebugeval-callfunction-method.md) 과 유사 합니다. 즉, 형식 매개 변수를 사용 하거나 둘 다를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="e8803-113">먼저 클래스에 대해 형식 인수를 지정 하 고 그 다음에 함수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="e8803-114">함수가 다른 응용 프로그램 도메인에 있는 경우 전환이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="e8803-115">그러나 모든 형식 및 값 인수는 대상 응용 프로그램 도메인에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="e8803-116">함수 실행은 제한 된 시나리오 에서만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="e8803-117">또는 `CallParameterizedFunction` `ICorDebugEval::CallFunction` 이 실패할 경우 반환 되는 HRESULT는 가장 일반적인 실패 이유를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8803-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8803-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8803-118">Requirements</span></span>  
 <span data-ttu-id="e8803-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e8803-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8803-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8803-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8803-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8803-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8803-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8803-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
