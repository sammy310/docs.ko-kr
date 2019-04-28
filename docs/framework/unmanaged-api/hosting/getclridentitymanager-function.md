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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84f71266d84cc98c2a5deb4aa8639e36808315a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628030"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="6ebdb-102">GetCLRIdentityManager 함수</span><span class="sxs-lookup"><span data-stu-id="6ebdb-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="6ebdb-103">CLR (공용 언어 런타임) id를 관리할 수 있도록 하는 인터페이스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ebdb-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="6ebdb-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebdb-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ebdb-105">구문</span><span class="sxs-lookup"><span data-stu-id="6ebdb-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ebdb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ebdb-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="6ebdb-107">[in] `REFIID` 가져오려는 인터페이스를 지정 하는 (인터페이스 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="6ebdb-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="6ebdb-108">이 값은 IID_ICLRAssemblyIdentityManager 또는 IID_ICLRHostBindingPolicyManager 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebdb-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="6ebdb-109">[out] 주소에 대 한 포인터를 [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) 요소나 [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6ebdb-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ebdb-110">설명</span><span class="sxs-lookup"><span data-stu-id="6ebdb-110">Remarks</span></span>  
 <span data-ttu-id="6ebdb-111">호출 된 [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) 함수에 대 한 포인터를는 `GetCLRIdentityManager` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ebdb-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ebdb-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ebdb-112">Requirements</span></span>  
 <span data-ttu-id="6ebdb-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ebdb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ebdb-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ebdb-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ebdb-115">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="6ebdb-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="6ebdb-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ebdb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ebdb-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="6ebdb-117">See also</span></span>

- [<span data-ttu-id="6ebdb-118">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="6ebdb-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
