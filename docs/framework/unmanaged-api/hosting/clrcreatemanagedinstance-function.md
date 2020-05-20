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
ms.openlocfilehash: ecd618ecf08836ea5e38ce738f97fc91ee6426f4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616816"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="fb3dc-102">ClrCreateManagedInstance 함수</span><span class="sxs-lookup"><span data-stu-id="fb3dc-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="fb3dc-103">지정 된 관리 되는 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="fb3dc-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="fb3dc-105">COM 활성화를 사용 하 여 관리 되는 형식의 인스턴스를 만들거나 호스팅을 사용 합니다 ( [.NET Framework 4 및 4.5에 추가 된 CLR 호스팅 인터페이스](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)참조).</span><span class="sxs-lookup"><span data-stu-id="fb3dc-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb3dc-106">구문</span><span class="sxs-lookup"><span data-stu-id="fb3dc-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb3dc-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb3dc-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="fb3dc-108">진행 요청 되는 인스턴스 형식의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="fb3dc-109">진행 `IID`요청 되는 인스턴스 형식의입니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="fb3dc-110">제한이 호출자가 요청한 관리 되는 형식의 인스턴스에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb3dc-111">설명</span><span class="sxs-lookup"><span data-stu-id="fb3dc-111">Remarks</span></span>  
 <span data-ttu-id="fb3dc-112">공용 언어 런타임이 이미 프로세스에 로드 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="fb3dc-113">예를 들어 함수를 호출 하기 전에 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 함수에 대 한 호출을 사용 하 여 로드할 수 있습니다 `ClrCreateManagedInstance` .</span><span class="sxs-lookup"><span data-stu-id="fb3dc-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="fb3dc-114">런타임이 로드 되지 않은 경우는 `ClrCreateManagedInstance` 먼저 런타임의 v v1.0.3705를 로드 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="fb3dc-115">이 작업이 실패 하면 최신 버전의 런타임을 로드 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb3dc-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb3dc-116">Requirements</span></span>  
 <span data-ttu-id="fb3dc-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb3dc-118">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fb3dc-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb3dc-119">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fb3dc-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb3dc-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb3dc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb3dc-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb3dc-121">See also</span></span>

- [<span data-ttu-id="fb3dc-122">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="fb3dc-122">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="fb3dc-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="fb3dc-123">Hosting</span></span>](index.md)
