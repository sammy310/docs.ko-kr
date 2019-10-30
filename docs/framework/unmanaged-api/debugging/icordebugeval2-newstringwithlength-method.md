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
ms.openlocfilehash: 3836b6c08098d38516c8a25260fb28998a2317fe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084778"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="79b09-102">ICorDebugEval2::NewStringWithLength 메서드</span><span class="sxs-lookup"><span data-stu-id="79b09-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="79b09-103">지정 된 내용을 사용 하 여 지정 된 길이의 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="79b09-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b09-104">구문</span><span class="sxs-lookup"><span data-stu-id="79b09-104">Syntax</span></span>  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79b09-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="79b09-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="79b09-106">진행 문자열 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="79b09-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="79b09-107">진행 문자열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="79b09-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79b09-108">주의</span><span class="sxs-lookup"><span data-stu-id="79b09-108">Remarks</span></span>  
 <span data-ttu-id="79b09-109">문자열의 후행 null 문자가 관리 되는 문자열에 있어야 하는 경우 `NewStringWithLength` 메서드의 호출자가 문자열 길이에 후행 null 문자를 포함 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b09-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="79b09-110">문자열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="79b09-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79b09-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="79b09-111">Requirements</span></span>  
 <span data-ttu-id="79b09-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79b09-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79b09-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79b09-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79b09-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79b09-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79b09-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79b09-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
