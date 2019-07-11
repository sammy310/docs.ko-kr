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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77c88786befb92960f4cfa4a960cbfc624318b26
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771599"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="f7e6b-102">ICorDebugStringValue::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="f7e6b-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="f7e6b-103">이 ICorDebugStringValue이 참조 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f7e6b-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7e6b-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7e6b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7e6b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7e6b-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="f7e6b-106">[in] `szString` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f7e6b-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="f7e6b-107">[out] 반환 된 문자 수에 대 한 포인터를 `szString` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f7e6b-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="f7e6b-108">[out] 검색된 문자열을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f7e6b-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7e6b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7e6b-109">Requirements</span></span>  
 <span data-ttu-id="f7e6b-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7e6b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7e6b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7e6b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7e6b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7e6b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7e6b-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7e6b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
