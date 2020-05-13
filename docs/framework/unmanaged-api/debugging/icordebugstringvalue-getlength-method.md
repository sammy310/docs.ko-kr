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
ms.openlocfilehash: 945e4ac88634c9103a722a180a4fe92a554ca53b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378889"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="c7cd2-102">ICorDebugStringValue::GetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="c7cd2-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="c7cd2-103">이 ICorDebugStringValue에서 참조 하는 문자열의 문자 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c7cd2-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7cd2-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7cd2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7cd2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7cd2-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="c7cd2-106">제한이 이 개체가 참조 하는 문자열의 길이를 지정 하는 값에 대 한 포인터입니다 `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="c7cd2-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7cd2-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7cd2-107">Requirements</span></span>  
 <span data-ttu-id="c7cd2-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7cd2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7cd2-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7cd2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7cd2-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7cd2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7cd2-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7cd2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
