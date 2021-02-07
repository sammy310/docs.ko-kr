---
description: '자세히 알아보기: ICorDebugEval:: NewString 메서드'
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
ms.openlocfilehash: 21eb49900d84cb1ad1f68a701998a4a778c3ef17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693839"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="dd872-103">ICorDebugEval::NewString 메서드</span><span class="sxs-lookup"><span data-stu-id="dd872-103">ICorDebugEval::NewString Method</span></span>

<span data-ttu-id="dd872-104">지정 된 내용을 사용 하 여 새 문자열 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd872-104">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd872-105">구문</span><span class="sxs-lookup"><span data-stu-id="dd872-105">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd872-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dd872-106">Parameters</span></span>  

 `string`  
 <span data-ttu-id="dd872-107">진행 문자열의 내용에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dd872-107">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd872-108">설명</span><span class="sxs-lookup"><span data-stu-id="dd872-108">Remarks</span></span>  

 <span data-ttu-id="dd872-109">문자열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="dd872-109">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd872-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd872-110">Requirements</span></span>  

 <span data-ttu-id="dd872-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd872-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd872-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd872-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd872-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd872-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd872-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd872-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
