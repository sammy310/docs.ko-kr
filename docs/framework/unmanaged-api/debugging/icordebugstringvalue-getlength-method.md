---
title: ICorDebugStringValue::GetLength 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
ms.openlocfilehash: 74a4b42be09c577cc80f1a73e077694e5a4a8d5f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697118"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="9590f-102">ICorDebugStringValue::GetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="9590f-102">ICorDebugStringValue::GetLength Method</span></span>

<span data-ttu-id="9590f-103">이 ICorDebugStringValue에서 참조 하는 문자열의 문자 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9590f-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9590f-104">구문</span><span class="sxs-lookup"><span data-stu-id="9590f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9590f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9590f-105">Parameters</span></span>  

 `pcchString`  
 <span data-ttu-id="9590f-106">제한이 이 개체가 참조 하는 문자열의 길이를 지정 하는 값에 대 한 포인터입니다 `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="9590f-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9590f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9590f-107">Requirements</span></span>  

 <span data-ttu-id="9590f-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9590f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9590f-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9590f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9590f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9590f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9590f-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9590f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
