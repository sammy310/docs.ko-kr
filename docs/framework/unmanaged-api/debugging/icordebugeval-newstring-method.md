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
ms.openlocfilehash: c2d29a0cc344539bf515793c071fe839aa441ebc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729722"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="7c95d-102">ICorDebugEval::NewString 메서드</span><span class="sxs-lookup"><span data-stu-id="7c95d-102">ICorDebugEval::NewString Method</span></span>

<span data-ttu-id="7c95d-103">지정 된 내용을 사용 하 여 새 문자열 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c95d-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c95d-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c95d-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c95d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c95d-105">Parameters</span></span>  

 `string`  
 <span data-ttu-id="7c95d-106">진행 문자열의 내용에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7c95d-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c95d-107">설명</span><span class="sxs-lookup"><span data-stu-id="7c95d-107">Remarks</span></span>  

 <span data-ttu-id="7c95d-108">문자열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7c95d-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c95d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c95d-109">Requirements</span></span>  

 <span data-ttu-id="7c95d-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c95d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c95d-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c95d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c95d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c95d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c95d-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c95d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
