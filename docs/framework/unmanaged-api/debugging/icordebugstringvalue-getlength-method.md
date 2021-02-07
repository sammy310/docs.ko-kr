---
description: '자세히 알아보기: ICorDebugStringValue:: GetLength 메서드'
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
ms.openlocfilehash: ae4d42b5b65e5f80e884415a5acfc7f894ffe11e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717383"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="46dd2-103">ICorDebugStringValue::GetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="46dd2-103">ICorDebugStringValue::GetLength Method</span></span>

<span data-ttu-id="46dd2-104">이 ICorDebugStringValue에서 참조 하는 문자열의 문자 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46dd2-104">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46dd2-105">구문</span><span class="sxs-lookup"><span data-stu-id="46dd2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46dd2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46dd2-106">Parameters</span></span>  

 `pcchString`  
 <span data-ttu-id="46dd2-107">제한이 이 개체가 참조 하는 문자열의 길이를 지정 하는 값에 대 한 포인터입니다 `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="46dd2-107">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46dd2-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46dd2-108">Requirements</span></span>  

 <span data-ttu-id="46dd2-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46dd2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46dd2-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46dd2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46dd2-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46dd2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46dd2-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46dd2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
