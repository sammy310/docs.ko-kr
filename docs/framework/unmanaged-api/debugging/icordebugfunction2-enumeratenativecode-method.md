---
title: ICorDebugFunction2::EnumerateNativeCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
ms.openlocfilehash: 2cac4a3120e842bde9ad708a251682421fd4ca93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696078"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="d70f6-102">ICorDebugFunction2::EnumerateNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="d70f6-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>

<span data-ttu-id="d70f6-103">이 ICorDebugFunction2 개체가 참조 하는 함수에 네이티브 코드 문을 포함 하는 ICorDebugCodeEnum 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d70f6-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d70f6-104">`EnumerateNativeCode` 는 현재 버전의 .NET Framework에서 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d70f6-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d70f6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d70f6-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d70f6-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d70f6-106">Requirements</span></span>  

 <span data-ttu-id="d70f6-107">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d70f6-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
