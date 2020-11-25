---
title: ICorDebugMDA::GetFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
ms.openlocfilehash: 38a5c2da900530b6bf78f24e224714496ceaa62c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710963"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="88ffa-102">ICorDebugMDA::GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="88ffa-102">ICorDebugMDA::GetFlags Method</span></span>

<span data-ttu-id="88ffa-103">[ICorDebugMDA](icordebugmda-interface.md)로 표시 된 MDA (관리 디버깅 도우미)와 연결 된 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88ffa-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88ffa-104">구문</span><span class="sxs-lookup"><span data-stu-id="88ffa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88ffa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88ffa-105">Parameters</span></span>  

 `pFlags`  
 <span data-ttu-id="88ffa-106">진행 이 MDA에 대 한 플래그의 설정을 지정 하는 [Cordebugmdaflags](cordebugmdaflags-enumeration.md) 열거형 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="88ffa-106">[in] A bitwise combination of the [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88ffa-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88ffa-107">Requirements</span></span>  

 <span data-ttu-id="88ffa-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88ffa-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88ffa-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88ffa-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88ffa-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88ffa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88ffa-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88ffa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88ffa-112">참조</span><span class="sxs-lookup"><span data-stu-id="88ffa-112">See also</span></span>

- [<span data-ttu-id="88ffa-113">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88ffa-113">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="88ffa-114">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="88ffa-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
