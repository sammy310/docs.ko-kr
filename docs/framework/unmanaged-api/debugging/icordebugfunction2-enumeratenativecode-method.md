---
description: '자세히 알아보기: ICorDebugFunction2:: EnumerateNativeCode 메서드'
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
ms.openlocfilehash: 617d6dbfdb596df192e2722a47d81517ae57ac1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692253"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="3f39d-103">ICorDebugFunction2::EnumerateNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="3f39d-103">ICorDebugFunction2::EnumerateNativeCode Method</span></span>

<span data-ttu-id="3f39d-104">이 ICorDebugFunction2 개체가 참조 하는 함수에 네이티브 코드 문을 포함 하는 ICorDebugCodeEnum 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f39d-104">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f39d-105">`EnumerateNativeCode` 는 현재 버전의 .NET Framework에서 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f39d-105">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f39d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f39d-106">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3f39d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f39d-107">Requirements</span></span>  

 <span data-ttu-id="3f39d-108">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f39d-108">**Header:** CorDebug.idl, CorDebug.h</span></span>
