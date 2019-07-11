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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9597d05e46c2d41ab1f24a073c028561e944fb59
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753036"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="141a3-102">ICorDebugEval::NewArray 메서드</span><span class="sxs-lookup"><span data-stu-id="141a3-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="141a3-103">지정 된 요소 형식 및 차원에는 새 배열을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="141a3-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="141a3-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="141a3-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="141a3-105">사용 하 여 [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="141a3-105">Use [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="141a3-106">구문</span><span class="sxs-lookup"><span data-stu-id="141a3-106">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="141a3-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="141a3-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="141a3-108">[in] 배열의 요소 형식을 지정 하는 CorElementType 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="141a3-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="141a3-109">[in] 요소의 클래스를 지정 하는 ICorDebugClass 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="141a3-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="141a3-110">이 값 요소 형식이 기본 형식인 경우에 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="141a3-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="141a3-111">[in] 배열의 차원 수입니다.</span><span class="sxs-lookup"><span data-stu-id="141a3-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="141a3-112">.NET Framework 2.0에서는이 값에는 1 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="141a3-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="141a3-113">[in] 바이트 배열의 각 차원 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="141a3-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="141a3-114">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="141a3-114">[in] Optional.</span></span> <span data-ttu-id="141a3-115">배열의 각 차원 하 한.</span><span class="sxs-lookup"><span data-stu-id="141a3-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="141a3-116">이 값을 생략 하는 경우에 각 차원에 대 한 하한값 0으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="141a3-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="141a3-117">설명</span><span class="sxs-lookup"><span data-stu-id="141a3-117">Remarks</span></span>  
 <span data-ttu-id="141a3-118">스레드가 현재 실행 중인 응용 프로그램 도메인에서 배열 항상 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="141a3-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="141a3-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="141a3-119">Requirements</span></span>  
 <span data-ttu-id="141a3-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="141a3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="141a3-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="141a3-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="141a3-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="141a3-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="141a3-123">**.NET framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="141a3-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
