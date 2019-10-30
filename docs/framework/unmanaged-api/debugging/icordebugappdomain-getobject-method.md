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
ms.openlocfilehash: f2c881603cfa0e4b3d2dc8d1e996631b51d1e850
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134708"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="343a5-102">ICorDebugAppDomain::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="343a5-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="343a5-103">CLR (공용 언어 런타임) 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="343a5-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="343a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="343a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="343a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="343a5-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="343a5-106">제한이 CLR 응용 프로그램 도메인을 나타내는 ICorDebugValue 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="343a5-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="343a5-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="343a5-107">Return Value</span></span>  
 <span data-ttu-id="343a5-108">관리 되는 <xref:System.AppDomain?displayProperty=nameWithType> 개체가이 응용 프로그램 도메인에 대해 생성 되지 않은 경우 메서드는 `S_FALSE`를 반환 하 고 `*ppObject`에 `NULL`를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="343a5-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="343a5-109">주의</span><span class="sxs-lookup"><span data-stu-id="343a5-109">Remarks</span></span>  
 <span data-ttu-id="343a5-110">프로세스의 각 응용 프로그램 도메인은이를 나타내는 런타임에 관리 되는 <xref:System.AppDomain?displayProperty=nameWithType> 개체를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a5-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="343a5-111">이 함수는이 관리 되는 <xref:System.AppDomain?displayProperty=nameWithType> 개체에 해당 하는 ICorDebugValue 인터페이스 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="343a5-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="343a5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="343a5-112">Requirements</span></span>  
 <span data-ttu-id="343a5-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="343a5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="343a5-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="343a5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="343a5-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="343a5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="343a5-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="343a5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
