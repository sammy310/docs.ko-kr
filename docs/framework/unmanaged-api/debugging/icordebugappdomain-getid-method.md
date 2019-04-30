---
title: ICorDebugAppDomain::GetId 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0aefc19ca0c255c9c8ea40fcc12fc5cba1b00f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996257"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="71c8f-102">ICorDebugAppDomain::GetId 메서드</span><span class="sxs-lookup"><span data-stu-id="71c8f-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="71c8f-103">응용 프로그램 도메인의 고유 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="71c8f-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71c8f-104">구문</span><span class="sxs-lookup"><span data-stu-id="71c8f-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71c8f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71c8f-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="71c8f-106">[out] 응용 프로그램 도메인의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="71c8f-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71c8f-107">설명</span><span class="sxs-lookup"><span data-stu-id="71c8f-107">Remarks</span></span>  
 <span data-ttu-id="71c8f-108">응용 프로그램 도메인의 식별자가 포함 하는 프로세스 내에서 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c8f-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71c8f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71c8f-109">Requirements</span></span>  
 <span data-ttu-id="71c8f-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71c8f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71c8f-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71c8f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71c8f-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71c8f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71c8f-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71c8f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
