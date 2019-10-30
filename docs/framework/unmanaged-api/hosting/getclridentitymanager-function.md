---
title: GetCLRIdentityManager 함수
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
ms.openlocfilehash: 3c6def32c63e3557a4de72baf7b1c3e67feb4891
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136523"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="f04f1-102">GetCLRIdentityManager 함수</span><span class="sxs-lookup"><span data-stu-id="f04f1-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="f04f1-103">CLR (공용 언어 런타임)에서 id를 관리할 수 있도록 하는 인터페이스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f04f1-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="f04f1-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f04f1-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f04f1-105">구문</span><span class="sxs-lookup"><span data-stu-id="f04f1-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f04f1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f04f1-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="f04f1-107">진행 가져올 인터페이스를 지정 하는 `REFIID` (인터페이스 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="f04f1-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="f04f1-108">이 값은 IID_ICLRAssemblyIdentityManager 또는 IID_ICLRHostBindingPolicyManager 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04f1-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="f04f1-109">제한이 [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) 또는 [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f04f1-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f04f1-110">주의</span><span class="sxs-lookup"><span data-stu-id="f04f1-110">Remarks</span></span>  
 <span data-ttu-id="f04f1-111">[GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) 함수를 호출 하 여 `GetCLRIdentityManager` 함수에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f04f1-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f04f1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f04f1-112">Requirements</span></span>  
 <span data-ttu-id="f04f1-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f04f1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f04f1-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f04f1-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f04f1-115">**라이브러리:** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="f04f1-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="f04f1-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f04f1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04f1-117">참조</span><span class="sxs-lookup"><span data-stu-id="f04f1-117">See also</span></span>

- [<span data-ttu-id="f04f1-118">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="f04f1-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
