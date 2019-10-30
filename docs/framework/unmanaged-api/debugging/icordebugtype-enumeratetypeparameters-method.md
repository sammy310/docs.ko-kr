---
title: ICorDebugType::EnumerateTypeParameters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
ms.openlocfilehash: 57a82e4ec106fead105cc7f200e7e56026004328
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122376"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="12f2b-102">ICorDebugType::EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="12f2b-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="12f2b-103">이 ICorDebugType에서 참조 하는 클래스의 <xref:System.Type> 매개 변수를 포함 하는 ICorDebugTypeEnum에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12f2b-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12f2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="12f2b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12f2b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12f2b-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="12f2b-106">제한이 형식의 매개 변수를 포함 하는 `ICorDebugTypeEnum`의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="12f2b-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12f2b-107">주의</span><span class="sxs-lookup"><span data-stu-id="12f2b-107">Remarks</span></span>  
 <span data-ttu-id="12f2b-108">[ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) 에서 반환 된 corelementtype 값이 ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR 또는 ELEMENT_TYPE_FNPTR 인 경우 `EnumerateTypeParameters`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f2b-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="12f2b-109">매개 변수 수와 해당 순서는 다음 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="12f2b-109">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="12f2b-110">ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE:이 메서드가 반환 하는 `ICorDebugTypeEnum`에 포함 된 형식 매개 변수의 수는 해당 클래스에 대 한 정식 형식 매개 변수의 수에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="12f2b-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="12f2b-111">예를 들어 형식이 `class Dict<String,int32>`이면 `EnumerateTypeParameters`는 `String`를 나타내는 개체와 순서 대로 `int32`를 포함 하는 `ICorDebugTypeEnum` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f2b-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="12f2b-112">ELEMENT_TYPE_FNPTR: `ICorDebugTypeEnum`에 포함 된 형식 매개 변수의 수는 함수에서 허용 하는 인수 개수 보다 1 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="12f2b-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="12f2b-113">`ICorDebugTypeEnum`에 포함 된 첫 번째 형식 매개 변수는 함수의 반환 형식이 고 후속 형식 매개 변수는 함수의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="12f2b-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="12f2b-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF 또는 ELEMENT_TYPE_PTR: 하나의 형식 매개 변수가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f2b-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="12f2b-115">예를 들어 형식이 `int32[]`와 같은 배열 형식인 경우`EnumerateTypeParameters`는 `int32`를 나타내는 개체를 포함 하는 `ICorDebugTypeEnum` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f2b-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12f2b-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12f2b-116">Requirements</span></span>  
 <span data-ttu-id="12f2b-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12f2b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12f2b-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12f2b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12f2b-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12f2b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12f2b-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12f2b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
