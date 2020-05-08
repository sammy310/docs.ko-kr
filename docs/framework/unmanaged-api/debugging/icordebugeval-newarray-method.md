---
title: ICorDebugEval::NewArray 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
ms.openlocfilehash: 496a6a7e01dec8aa90ba4e849c431ccd499ef53d
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976202"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="3462d-102">ICorDebugEval::NewArray 메서드</span><span class="sxs-lookup"><span data-stu-id="3462d-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="3462d-103">지정 된 요소 형식 및 차원의 새 배열을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="3462d-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="3462d-105">대신 [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-105">Use [ICorDebugEval2::NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3462d-106">구문</span><span class="sxs-lookup"><span data-stu-id="3462d-106">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3462d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3462d-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="3462d-108">진행 배열의 요소 형식을 지정 하는 CorElementType 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="3462d-109">진행 요소의 클래스를 지정 하는 ICorDebugClass 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="3462d-110">요소 형식이 기본 형식인 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="3462d-111">진행 배열의 차원 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="3462d-112">.NET Framework 2.0에서이 값은 1 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="3462d-113">진행 배열의 각 차원 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="3462d-114">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="3462d-114">[in] Optional.</span></span> <span data-ttu-id="3462d-115">배열의 각 차원에 대 한 하 한입니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="3462d-116">이 값을 생략 하면 각 차원에 대해 하 한이 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3462d-117">설명</span><span class="sxs-lookup"><span data-stu-id="3462d-117">Remarks</span></span>  
 <span data-ttu-id="3462d-118">배열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3462d-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3462d-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3462d-119">Requirements</span></span>  
 <span data-ttu-id="3462d-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3462d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3462d-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3462d-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3462d-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3462d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3462d-123">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="3462d-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
