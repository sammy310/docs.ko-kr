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
ms.openlocfilehash: b263fed7db5cb2ef687da45f8cbc99a02e1e3ea2
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976137"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="b8efe-102">ICorDebugEval::NewString 메서드</span><span class="sxs-lookup"><span data-stu-id="b8efe-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="b8efe-103">지정 된 내용을 사용 하 여 새 문자열 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8efe-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8efe-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8efe-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8efe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8efe-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="b8efe-106">진행 문자열의 내용에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b8efe-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8efe-107">설명</span><span class="sxs-lookup"><span data-stu-id="b8efe-107">Remarks</span></span>  
 <span data-ttu-id="b8efe-108">문자열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b8efe-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8efe-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8efe-109">Requirements</span></span>  
 <span data-ttu-id="b8efe-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8efe-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8efe-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8efe-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8efe-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8efe-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8efe-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8efe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
