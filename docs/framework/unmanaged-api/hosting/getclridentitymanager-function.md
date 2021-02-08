---
description: '자세히 알아보기: GetCLRIdentityManager 함수'
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
ms.openlocfilehash: 483cf0499fa162da4c89e350198a5609f9f1bab6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785369"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="f0e17-103">GetCLRIdentityManager 함수</span><span class="sxs-lookup"><span data-stu-id="f0e17-103">GetCLRIdentityManager Function</span></span>

<span data-ttu-id="f0e17-104">CLR (공용 언어 런타임)에서 id를 관리할 수 있도록 하는 인터페이스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f0e17-104">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="f0e17-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e17-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e17-106">구문</span><span class="sxs-lookup"><span data-stu-id="f0e17-106">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0e17-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0e17-107">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="f0e17-108">진행 `REFIID` 가져올 인터페이스를 지정 하는 (인터페이스 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e17-108">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="f0e17-109">이 값은 IID_ICLRAssemblyIdentityManager 또는 IID_ICLRHostBindingPolicyManager 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e17-109">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="f0e17-110">제한이 [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) 또는 [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e17-110">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0e17-111">설명</span><span class="sxs-lookup"><span data-stu-id="f0e17-111">Remarks</span></span>  

 <span data-ttu-id="f0e17-112">[GetRealProcAddress](getrealprocaddress-function.md) 함수를 호출 하 여 함수에 대 한 포인터를 가져옵니다 `GetCLRIdentityManager` .</span><span class="sxs-lookup"><span data-stu-id="f0e17-112">Call the [GetRealProcAddress](getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0e17-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0e17-113">Requirements</span></span>  

 <span data-ttu-id="f0e17-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e17-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0e17-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f0e17-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0e17-116">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="f0e17-116">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="f0e17-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0e17-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0e17-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0e17-118">See also</span></span>

- [<span data-ttu-id="f0e17-119">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="f0e17-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
