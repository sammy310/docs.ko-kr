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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b168673e76beddd8ae0479b8daae009c5f057b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987378"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="adb23-102">ICorDebugStringValue::GetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="adb23-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="adb23-103">이 ICorDebugStringValue이 참조 하는 문자열의 문자 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="adb23-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adb23-104">구문</span><span class="sxs-lookup"><span data-stu-id="adb23-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adb23-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="adb23-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="adb23-106">[out] 이 참조 하는 문자열의 길이 지정 하는 값에 대 한 포인터 `ICorDebugStringValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="adb23-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adb23-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="adb23-107">Requirements</span></span>  
 <span data-ttu-id="adb23-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="adb23-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adb23-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adb23-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="adb23-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adb23-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adb23-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adb23-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
