---
title: ICorDebugAppDomain2::GetFunctionPointerType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f0643ba9e750e7c64d2dae8eb5744df7bc26931
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737795"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="06011-102">ICorDebugAppDomain2::GetFunctionPointerType 메서드</span><span class="sxs-lookup"><span data-stu-id="06011-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="06011-103">지정 된 시그니처가 있는 함수에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="06011-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06011-104">구문</span><span class="sxs-lookup"><span data-stu-id="06011-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06011-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06011-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="06011-106">[in] 함수에 대 한 형식 인수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="06011-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="06011-107">[in] 함수의 형식 인수를 나타내는 ICorDebugType 개체를 가리키는 각각 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="06011-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="06011-108">첫 번째 요소는 반환 형식입니다. 각각의 다른 요소에는 매개 변수 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="06011-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="06011-109">[out] 주소에 대 한 포인터는 `ICorDebugType` 함수에 대 한 포인터를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="06011-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06011-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06011-110">Requirements</span></span>  
 <span data-ttu-id="06011-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="06011-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06011-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06011-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06011-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06011-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06011-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06011-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
