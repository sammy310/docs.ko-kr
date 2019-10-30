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
ms.openlocfilehash: 4e672030ae83b57da6f9ab66630513d79f28b8f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131993"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="30106-102">ClrCreateManagedInstance 함수</span><span class="sxs-lookup"><span data-stu-id="30106-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="30106-103">지정 된 관리 되는 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30106-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="30106-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30106-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="30106-105">COM 활성화를 사용 하 여 관리 되는 형식의 인스턴스를 만들거나 호스팅을 사용 합니다 ( [.NET Framework 4 및 4.5에 추가 된 CLR 호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)참조).</span><span class="sxs-lookup"><span data-stu-id="30106-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30106-106">구문</span><span class="sxs-lookup"><span data-stu-id="30106-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30106-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="30106-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="30106-108">진행 요청 되는 인스턴스 형식의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="30106-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="30106-109">진행 요청 중인 인스턴스 유형의 `IID`입니다.</span><span class="sxs-lookup"><span data-stu-id="30106-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="30106-110">제한이 호출자가 요청한 관리 되는 형식의 인스턴스에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="30106-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30106-111">주의</span><span class="sxs-lookup"><span data-stu-id="30106-111">Remarks</span></span>  
 <span data-ttu-id="30106-112">공용 언어 런타임이 이미 프로세스에 로드 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30106-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="30106-113">예를 들어 `ClrCreateManagedInstance` 함수를 호출 하기 전에 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수에 대 한 호출을 사용 하 여 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30106-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="30106-114">런타임이 로드 되지 않은 경우 `ClrCreateManagedInstance` 먼저 런타임의 v v1.0.3705 로드를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="30106-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="30106-115">이 작업이 실패 하면 최신 버전의 런타임을 로드 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="30106-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30106-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30106-116">Requirements</span></span>  
 <span data-ttu-id="30106-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30106-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30106-118">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="30106-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30106-119">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="30106-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30106-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30106-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30106-121">참조</span><span class="sxs-lookup"><span data-stu-id="30106-121">See also</span></span>

- [<span data-ttu-id="30106-122">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="30106-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="30106-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="30106-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
