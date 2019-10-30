---
title: ICorDebugEval2::NewParameterizedArray 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
ms.openlocfilehash: 9476bcc9706e89fd3d7e0abc14031f70a0aa0ad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084834"
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="9fcaa-102">ICorDebugEval2::NewParameterizedArray 메서드</span><span class="sxs-lookup"><span data-stu-id="9fcaa-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="9fcaa-103">지정 된 요소 형식 및 차원의 새 배열을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcaa-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fcaa-104">구문</span><span class="sxs-lookup"><span data-stu-id="9fcaa-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fcaa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9fcaa-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="9fcaa-106">진행 배열에 저장 된 요소의 형식을 나타내는 ICorDebugType 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9fcaa-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="9fcaa-107">진행 배열의 차원 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9fcaa-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="9fcaa-108">.NET Framework 버전 2.0에서이 값은 1 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcaa-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="9fcaa-109">진행 배열의 각 차원 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="9fcaa-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="9fcaa-110">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="9fcaa-110">[in] Optional.</span></span> <span data-ttu-id="9fcaa-111">배열의 각 차원에 대 한 하 한입니다.</span><span class="sxs-lookup"><span data-stu-id="9fcaa-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="9fcaa-112">이 값을 생략 하면 각 차원에 대해 하 한이 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fcaa-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fcaa-113">주의</span><span class="sxs-lookup"><span data-stu-id="9fcaa-113">Remarks</span></span>  
 <span data-ttu-id="9fcaa-114">배열의 요소는 제네릭 형식의 인스턴스인 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fcaa-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="9fcaa-115">배열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9fcaa-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="9fcaa-116">.NET Framework 2.0에서 `rank` 값은 1 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcaa-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fcaa-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9fcaa-117">Requirements</span></span>  
 <span data-ttu-id="9fcaa-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fcaa-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fcaa-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fcaa-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fcaa-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fcaa-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fcaa-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fcaa-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
