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
ms.openlocfilehash: e34dff2ebdb6e1ea56c2682b351c3e17a44416f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726316"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="f2518-102">ICorDebugFunction::GetNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="f2518-102">ICorDebugFunction::GetNativeCode Method</span></span>

<span data-ttu-id="f2518-103">이 ICorDebugFunction 인스턴스로 표시 되는 함수에 대 한 네이티브 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f2518-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2518-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2518-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2518-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2518-105">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="f2518-106">제한이 이 함수에 대 한 네이티브 코드를 나타내는 ICorDebugCode 인스턴스에 대 한 포인터 이거나,이 함수가 JIT (just-in-time) 컴파일되지 않은 MSIL (Microsoft 중간 언어) 코드 인 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="f2518-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2518-107">설명</span><span class="sxs-lookup"><span data-stu-id="f2518-107">Remarks</span></span>  

 <span data-ttu-id="f2518-108">이 인스턴스가 나타내는 함수가 `ICorDebugFunction` 제네릭 형식의 경우와 같이 두 번 이상 JIT 컴파일된 경우 `GetNativeCode` 임의의 네이티브 코드 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2518-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2518-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2518-109">Requirements</span></span>  

 <span data-ttu-id="f2518-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2518-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2518-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2518-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2518-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2518-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2518-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2518-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
