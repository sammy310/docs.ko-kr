---
title: ICorDebugEval::NewString 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
ms.openlocfilehash: 8a5d421bf0eb8ec5a34fe21d6efc79bbe56c294c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137652"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="f71e5-102">ICorDebugEval::NewString 메서드</span><span class="sxs-lookup"><span data-stu-id="f71e5-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="f71e5-103">지정 된 내용을 사용 하 여 새 문자열 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e5-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f71e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="f71e5-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f71e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f71e5-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="f71e5-106">진행 문자열의 내용에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f71e5-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f71e5-107">주의</span><span class="sxs-lookup"><span data-stu-id="f71e5-107">Remarks</span></span>  
 <span data-ttu-id="f71e5-108">문자열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f71e5-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f71e5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f71e5-109">Requirements</span></span>  
 <span data-ttu-id="f71e5-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f71e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f71e5-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f71e5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f71e5-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f71e5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f71e5-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f71e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
