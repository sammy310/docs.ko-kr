---
title: ICorDebugModule::GetGlobalVariableValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetGlobalVariableValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetGlobalVariableValue
helpviewer_keywords:
- ICorDebugModule::GetGlobalVariableValue method [.NET Framework debugging]
- GetGlobalVariableValue method [.NET Framework debugging]
ms.assetid: bbc0881c-6a59-41a0-b5ee-2f3d1b71684c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00e747e43f67533771665313f4d420e4725945cd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485354"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="46941-102">ICorDebugModule::GetGlobalVariableValue 메서드</span><span class="sxs-lookup"><span data-stu-id="46941-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="46941-103">지정 된 전역 변수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46941-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46941-104">구문</span><span class="sxs-lookup"><span data-stu-id="46941-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46941-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46941-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="46941-106">[in] `mdFieldDef` 전역 변수를 설명 하는 메타 데이터를 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="46941-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="46941-107">[out] 지정 된 전역 변수의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46941-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46941-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46941-108">Requirements</span></span>  
 <span data-ttu-id="46941-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="46941-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46941-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46941-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46941-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46941-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46941-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46941-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
