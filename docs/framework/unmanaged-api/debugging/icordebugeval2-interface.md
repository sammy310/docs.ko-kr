---
title: ICorDebugEval2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
ms.openlocfilehash: b597d95b5b25e5ebf04fac48e4f3fda312a9594c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976124"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="7c0ad-102">ICorDebugEval2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c0ad-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="7c0ad-103">"ICorDebugEval"를 확장 하 여 제네릭 형식에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ad-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c0ad-104">메서드</span><span class="sxs-lookup"><span data-stu-id="7c0ad-104">Methods</span></span>  
  
|<span data-ttu-id="7c0ad-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7c0ad-105">Method</span></span>|<span data-ttu-id="7c0ad-106">Description</span><span class="sxs-lookup"><span data-stu-id="7c0ad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c0ad-107">CallParameterizedFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="7c0ad-107">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="7c0ad-108">지정 된 "ICorDebugFunction"에 대 한 호출을 설정 합니다 .이는 생성자에서 형식 매개 변수를 사용 하거나 형식 매개 변수를 사용할 수 있는 형식 내에 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ad-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="7c0ad-109">CreateValueForType 메서드</span><span class="sxs-lookup"><span data-stu-id="7c0ad-109">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="7c0ad-110">초기 값이 null 또는 0 인 지정 된 형식의 새 "ICorDebugValue"에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ad-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="7c0ad-111">NewParameterizedArray 메서드</span><span class="sxs-lookup"><span data-stu-id="7c0ad-111">NewParameterizedArray Method</span></span>](icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="7c0ad-112">지정 된 요소 형식 및 차원의 새 배열을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ad-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="7c0ad-113">NewParameterizedObject 메서드</span><span class="sxs-lookup"><span data-stu-id="7c0ad-113">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="7c0ad-114">매개 변수가 있는 새 형식 개체를 인스턴스화하고 개체의 생성자 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ad-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="7c0ad-115">NewParameterizedObjectNoConstructor 메서드</span><span class="sxs-lookup"><span data-stu-id="7c0ad-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="7c0ad-116">생성자 메서드 호출을 시도 하지 않고 지정 된 클래스의 매개 변수가 있는 새 형식 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ad-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="7c0ad-117">NewStringWithLength 메서드</span><span class="sxs-lookup"><span data-stu-id="7c0ad-117">NewStringWithLength Method</span></span>](icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="7c0ad-118">지정 된 내용을 사용 하 여 지정 된 길이의 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ad-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="7c0ad-119">RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="7c0ad-119">RudeAbort Method</span></span>](icordebugeval2-rudeabort-method.md)|<span data-ttu-id="7c0ad-120">현재 수행 중인 계산 `ICorDebugEval2` 을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ad-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c0ad-121">설명</span><span class="sxs-lookup"><span data-stu-id="7c0ad-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c0ad-122">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ad-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c0ad-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c0ad-123">Requirements</span></span>  
 <span data-ttu-id="7c0ad-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c0ad-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c0ad-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c0ad-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c0ad-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c0ad-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c0ad-127">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c0ad-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c0ad-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c0ad-128">See also</span></span>

- [<span data-ttu-id="7c0ad-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c0ad-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
