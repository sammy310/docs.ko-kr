---
title: ICorDebugStringValue::GetString 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
ms.openlocfilehash: c4b01b2c346d3173b2a5ecc144474d7fb1e6dce5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138967"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="b41d6-102">ICorDebugStringValue::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="b41d6-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="b41d6-103">이 ICorDebugStringValue에서 참조 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b41d6-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b41d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="b41d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b41d6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b41d6-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="b41d6-106">[in] `szString` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b41d6-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="b41d6-107">제한이 `szString` 배열에 반환 된 문자 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b41d6-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="b41d6-108">제한이 검색 된 문자열을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b41d6-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b41d6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b41d6-109">Requirements</span></span>  
 <span data-ttu-id="b41d6-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b41d6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b41d6-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b41d6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b41d6-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b41d6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b41d6-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b41d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
