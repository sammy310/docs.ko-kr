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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db609bdee7975b6c067271f99529e2cf2240f720
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989029"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="692a6-102">ICorDebugEval::NewString 메서드</span><span class="sxs-lookup"><span data-stu-id="692a6-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="692a6-103">지정된 된 콘텐츠를 사용 하 여 새 문자열 인스턴스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="692a6-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="692a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="692a6-104">Syntax</span></span>  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="692a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="692a6-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="692a6-106">[in] 문자열에 대 한 내용에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="692a6-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="692a6-107">설명</span><span class="sxs-lookup"><span data-stu-id="692a6-107">Remarks</span></span>  
 <span data-ttu-id="692a6-108">스레드가 현재 실행 중인 응용 프로그램 도메인에서 문자열 항상 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="692a6-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="692a6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="692a6-109">Requirements</span></span>  
 <span data-ttu-id="692a6-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="692a6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="692a6-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="692a6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="692a6-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="692a6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="692a6-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="692a6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
