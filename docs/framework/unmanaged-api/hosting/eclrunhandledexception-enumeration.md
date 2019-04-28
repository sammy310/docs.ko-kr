---
title: EClrUnhandledException 열거형
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e5fb3ab1d2dedb220fd4a486409512414233021
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795973"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="69479-102">EClrUnhandledException 열거형</span><span class="sxs-lookup"><span data-stu-id="69479-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="69479-103">사용자 코드에서 처리 되지 않은 예외를 관리 하기 위한 사용 가능한 옵션을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="69479-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69479-104">구문</span><span class="sxs-lookup"><span data-stu-id="69479-104">Syntax</span></span>  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="69479-105">멤버</span><span class="sxs-lookup"><span data-stu-id="69479-105">Members</span></span>  
  
|<span data-ttu-id="69479-106">멤버</span><span class="sxs-lookup"><span data-stu-id="69479-106">Member</span></span>|<span data-ttu-id="69479-107">설명</span><span class="sxs-lookup"><span data-stu-id="69479-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="69479-108">기본 동작 발생 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="69479-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="69479-109">프로세스 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69479-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="69479-110">CLR (공용 언어 런타임) 처리 되지 않은 예외를 무시 하 고 추가 작업을 확인 하 고 호스트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="69479-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69479-111">설명</span><span class="sxs-lookup"><span data-stu-id="69479-111">Remarks</span></span>  
 <span data-ttu-id="69479-112">CLR 버전 처럼 지정 하려면 사용 된 `eHostDeterminedPolicy` 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="69479-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69479-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69479-113">Requirements</span></span>  
 <span data-ttu-id="69479-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="69479-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69479-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="69479-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69479-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69479-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69479-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69479-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69479-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="69479-118">See also</span></span>

- [<span data-ttu-id="69479-119">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="69479-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="69479-120">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="69479-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="69479-121">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69479-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="69479-122">SetUnhandledExceptionPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="69479-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="69479-123">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69479-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="69479-124">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="69479-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
