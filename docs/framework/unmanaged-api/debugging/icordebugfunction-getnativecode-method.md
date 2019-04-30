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
ms.openlocfilehash: bb85c4b2c26c136a5f9fc05221a42c4bc99f37f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988704"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="6ace8-102">ICorDebugFunction::GetNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="6ace8-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="6ace8-103">ICorDebugFunction 인스턴스에 의해 표현 되는 함수에 대 한 네이티브 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ace8-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ace8-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ace8-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ace8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ace8-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="6ace8-106">[out] 이 함수는 Microsoft intermediate language (MSIL) 코드-just-in-time (JIT) 컴파일된 되지 않은 경우이 함수 또는 null에 대 한 네이티브 코드를 나타내는 ICorDebugCode 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6ace8-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ace8-107">설명</span><span class="sxs-lookup"><span data-stu-id="6ace8-107">Remarks</span></span>  
 <span data-ttu-id="6ace8-108">하는 경우이 표시 되는 함수 `ICorDebugFunction` 인스턴스는 JIT 컴파일된 두 번 이상 제네릭 형식을 경우와 같이 `GetNativeCode` 임의 네이티브 코드 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ace8-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ace8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ace8-109">Requirements</span></span>  
 <span data-ttu-id="6ace8-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ace8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ace8-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ace8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ace8-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ace8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ace8-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ace8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
