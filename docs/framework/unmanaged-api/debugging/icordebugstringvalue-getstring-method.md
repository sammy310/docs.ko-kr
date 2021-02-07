---
description: '자세히 알아보기: ICorDebugStringValue:: GetString 메서드'
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
ms.openlocfilehash: 06e8e039c8b0afb7753a398302a9b32eb3ba7213
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717344"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="40206-103">ICorDebugStringValue::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="40206-103">ICorDebugStringValue::GetString Method</span></span>

<span data-ttu-id="40206-104">이 ICorDebugStringValue에서 참조 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40206-104">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40206-105">구문</span><span class="sxs-lookup"><span data-stu-id="40206-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40206-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40206-106">Parameters</span></span>  

 `cchString`  
 <span data-ttu-id="40206-107">[in] `szString` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="40206-107">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="40206-108">제한이 배열에 반환 된 문자 수에 대 한 포인터 `szString` 입니다.</span><span class="sxs-lookup"><span data-stu-id="40206-108">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="40206-109">제한이 검색 된 문자열을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="40206-109">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40206-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40206-110">Requirements</span></span>  

 <span data-ttu-id="40206-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40206-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40206-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40206-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40206-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40206-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40206-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40206-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
