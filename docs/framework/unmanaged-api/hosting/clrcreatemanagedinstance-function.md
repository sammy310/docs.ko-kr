---
title: ClrCreateManagedInstance 함수
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: 7fbe0cf3e93d75749fa3f463f3f97dbd1bfe27a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176541"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="484a5-102">ClrCreateManagedInstance 함수</span><span class="sxs-lookup"><span data-stu-id="484a5-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="484a5-103">지정된 관리 되는 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="484a5-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="484a5-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="484a5-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="484a5-105">COM 활성화를 사용하여 관리되는 형식의 인스턴스를 만들거나 [호스팅을 사용합니다(.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)참조).</span><span class="sxs-lookup"><span data-stu-id="484a5-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="484a5-106">구문</span><span class="sxs-lookup"><span data-stu-id="484a5-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="484a5-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="484a5-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="484a5-108">【인】 요청되는 인스턴스 유형의 이름에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="484a5-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="484a5-109">【인】 요청중인 인스턴스 `IID` 유형의 입니다.</span><span class="sxs-lookup"><span data-stu-id="484a5-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="484a5-110">【아웃】 호출자에서 요청한 관리 되는 형식의 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="484a5-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="484a5-111">설명</span><span class="sxs-lookup"><span data-stu-id="484a5-111">Remarks</span></span>  
 <span data-ttu-id="484a5-112">공통 언어 런타임은 이미 프로세스에 로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="484a5-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="484a5-113">예를 들어 함수가 호출되기 전에 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수에 `ClrCreateManagedInstance` 대한 호출을 사용하여 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="484a5-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="484a5-114">런타임이 로드되지 않은 `ClrCreateManagedInstance` 경우 먼저 런타임의 v1.0.3705를 로드하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="484a5-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="484a5-115">실패하면 최신 버전의 런타임을 로드하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="484a5-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="484a5-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="484a5-116">Requirements</span></span>  
 <span data-ttu-id="484a5-117">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="484a5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="484a5-118">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="484a5-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="484a5-119">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="484a5-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="484a5-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="484a5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="484a5-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="484a5-121">See also</span></span>

- [<span data-ttu-id="484a5-122">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="484a5-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="484a5-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="484a5-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
