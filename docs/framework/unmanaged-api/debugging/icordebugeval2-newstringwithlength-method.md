---
title: ICorDebugEval2::NewStringWithLength 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b84a2fad53feda2996515781035c0eaad5828d54
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473437"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="a932f-102">ICorDebugEval2::NewStringWithLength 메서드</span><span class="sxs-lookup"><span data-stu-id="a932f-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="a932f-103">지정된 된 콘텐츠를 사용 하 여 지정 된 길이의 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a932f-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a932f-104">구문</span><span class="sxs-lookup"><span data-stu-id="a932f-104">Syntax</span></span>  
  
```  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a932f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a932f-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="a932f-106">[in] 문자열 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a932f-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="a932f-107">[in] 문자열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="a932f-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a932f-108">설명</span><span class="sxs-lookup"><span data-stu-id="a932f-108">Remarks</span></span>  
 <span data-ttu-id="a932f-109">경우 문자열의 후행 null 문자 이어야 하는데 관리 되는 문자열에서 호출자는 `NewStringWithLength` 메서드 문자열 길이 후행 null 문자를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a932f-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="a932f-110">스레드가 현재 실행 중인 응용 프로그램 도메인에서 문자열 항상 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a932f-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a932f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a932f-111">Requirements</span></span>  
 <span data-ttu-id="a932f-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a932f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a932f-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a932f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a932f-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a932f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a932f-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a932f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
