---
title: ICorDebugAppDomain::GetObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ca9792df69f859e20f1d9e40754d1cec138945d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480028"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="8119d-102">ICorDebugAppDomain::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="8119d-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="8119d-103">공용 언어 런타임 (CLR) 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8119d-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8119d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8119d-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8119d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8119d-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="8119d-106">[out] CLR 응용 프로그램 도메인을 나타내는 ICorDebugValue 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8119d-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8119d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8119d-107">Return Value</span></span>  
 <span data-ttu-id="8119d-108">관리 되는 경우 <xref:System.AppDomain?displayProperty=nameWithType> 이 응용 프로그램 도메인에 대 한 개체 생성 되지 않은, 메서드가 반환 `S_FALSE` 배치 `NULL` 에서 `*ppObject`합니다.</span><span class="sxs-lookup"><span data-stu-id="8119d-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8119d-109">설명</span><span class="sxs-lookup"><span data-stu-id="8119d-109">Remarks</span></span>  
 <span data-ttu-id="8119d-110">프로세스에서 각 응용 프로그램 도메인을 관리 되는 있을 <xref:System.AppDomain?displayProperty=nameWithType> 런타임에서 점을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8119d-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="8119d-111">이 함수는 관리 되는이에 해당 하는 ICorDebugValue 인터페이스 개체를 가져옵니다 <xref:System.AppDomain?displayProperty=nameWithType> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8119d-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8119d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8119d-112">Requirements</span></span>  
 <span data-ttu-id="8119d-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8119d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8119d-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8119d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8119d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8119d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8119d-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8119d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
