---
title: ICorDebugFunction::GetNativeCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0507d59011f6b584ecb1ae11c35c456c80793af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754589"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="3060d-102">ICorDebugFunction::GetNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="3060d-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="3060d-103">ICorDebugFunction 인스턴스에 의해 표현 되는 함수에 대 한 네이티브 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3060d-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3060d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3060d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3060d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3060d-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="3060d-106">[out] 이 함수는 Microsoft intermediate language (MSIL) 코드-just-in-time (JIT) 컴파일된 되지 않은 경우이 함수 또는 null에 대 한 네이티브 코드를 나타내는 ICorDebugCode 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3060d-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3060d-107">설명</span><span class="sxs-lookup"><span data-stu-id="3060d-107">Remarks</span></span>  
 <span data-ttu-id="3060d-108">하는 경우이 표시 되는 함수 `ICorDebugFunction` 인스턴스는 JIT 컴파일된 두 번 이상 제네릭 형식을 경우와 같이 `GetNativeCode` 임의 네이티브 코드 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3060d-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3060d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3060d-109">Requirements</span></span>  
 <span data-ttu-id="3060d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3060d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3060d-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3060d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3060d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3060d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3060d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3060d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
